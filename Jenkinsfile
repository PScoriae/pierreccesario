pipeline {

    agent any
    
    stages {
        stage("Hugo Build") {
            steps {
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