# static-jenkins
static website with jenkins pipeline


```
pipeline {
    agent any
    stages {
        stage ('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'us-west-2') {
                    s3Upload(bucket:'jenkins-static-pipeline-udacity', file:'index.html', path:'')
                }
            }
        }
    }
}
```
