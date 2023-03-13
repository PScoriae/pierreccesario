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
            when { changeset "main/**/*"}
            steps {
                dir('main') {
                    sh 'aws s3 cp public s3://pierreccesario.com --recursive'
                }
            }
        }
        stage("Push Music Files to S3 Bucket") {
            when { changeset "music/**/*"}
            steps {
                dir('music') {
                    sh 'aws s3 cp public s3://music.pierreccesario.com --recursive'
                }
            }
        }
    }
}