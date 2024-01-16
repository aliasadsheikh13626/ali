pipeline {
    agent any

    environment {
        AWS_REGION = 'us-east-1'
        AWS_PROFILE = "Ali's AWS"
        EC2_INSTANCE_ID = 'i-041a774d7ba18abfe'
        S3_BUCKET = 'Alikabucket'
    }

    stages {
        stage('Checkout') {
            steps {
                // Git checkout step with branch specified as 'main'
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'https://github.com/aliasadsheikh13626/ali.git']]])
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment steps here
            }
        }

        stage('Notify') {
            steps {
                echo 'Sending notifications...'
                // Add notification steps here
            }
        }
    }

    post {
        success {
            echo 'Pipeline successfully completed!'
        }
        failure {
            echo 'Pipeline failed! Take necessary actions...'
        }
    }
}

