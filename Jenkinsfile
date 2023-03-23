pipeline {

    agent any
    
    stages {
        stage("Hugo Build Main Site") {
            when { changeset "main/**/*"}
            steps {
                dir('main') {
                    sh 'sudo /usr/local/bin/hugo'
                }
            }
        }
        stage("Hugo Build Music Site") {
            when { changeset "music/**/*"}
            steps {
                dir('music') {
                    sh 'sudo /usr/local/bin/hugo'
                }
            }
        }

        stage("Push Main Files to S3 Bucket") {
            steps {
                dir('main') {
                    sh 'hugo deploy'
                }
            }
        }
        stage("Push Music Files to S3 Bucket") {
            steps {
                dir('music') {
                    sh 'hugo deploy'
                }
            }
        }
    }
}