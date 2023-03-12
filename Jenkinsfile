pipeline {

    agent any
    
    stages {
        stage("Hugo Build") {
            steps {
                dir('main') {
                    sh 'sudo /usr/local/bin/hugo'
                }
            }
        }
        stage("Push Files to S3 Bucket") {
            steps {
                dir('main') {
                    sh 'aws s3 cp public s3://pierreccesario.com --recursive'
                }
            }
        }
    }
}