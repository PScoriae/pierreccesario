pipeline {

    agent any
    
    stages {
        stage("Hugo Build") {
            steps {
                sh 'sudo /usr/local/bin/hugo'
            }
        }
        stage("Push Files to S3 Bucket") {
            steps {
                sh 'aws s3 cp -R public s3://pierreccesario.com'
            }
        }
    }
}