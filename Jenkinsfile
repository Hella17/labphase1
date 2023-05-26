pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Add your build steps here
                sh 'npm install' // Example: Installing dependencies
            }
        }

        stage('Test') {
            steps {
                // Add your test steps here
                sh 'npm test' // Example: Running tests
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                sh 'npm run deploy' // Example: Deploying the application
            }
        }
    }
}
