pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                pwd(); 
                withAWS(region:'us-west-2',credentials:'aws-static') {
                    // def identity=awsIdentity();
                    s3Upload(bucket:"jenkins-static-pipeline-udacity", file:'index.html', path:'/');
                }
            }
        }
    }
}