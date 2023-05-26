pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the backend application...'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the backend application...'
                // Add deployment steps here
            }
        }
    }

    post {
        always {
            echo 'Performing post-build actions...'
            // Clean up steps, if any
        }

        success {
            echo 'Pipeline succeeded!'
            // Success actions, if any
        }

        failure {
            echo 'Pipeline failed!'
            // Failure actions, if any
        }
    }
}
