pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'us-west-2') {
                    s3Upload(bucket:"jenkins-static-pipeline-udacity", file:'index.html', path:'');
                }
            }
        }
    }
}