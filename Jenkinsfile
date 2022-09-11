pipeline {

    agent any
    
    stages {
        stage("Hugo Build") {
            steps {
                dir("pierreccesario") {
                    sh "echo pwd"
                    sh "pwd"
                }
                sh 'hugo'
            }
        }
        stage("Push Files to S3 Bucket") {
            steps {
                sh 'echo something'
            }
        }
    }
}