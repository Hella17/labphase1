pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the front-end application...'
                echo 'Build completed!'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                echo 'Tests completed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the front-end application...'
                sh 'scp index.html user@your-web-server:/path/to/destination'
                sh 'scp styles.css user@your-web-server:/path/to/destination'
                sh 'scp index.js user@your-web-server:/path/to/destination'
                echo 'Deployment completed!'
            }
        }
    }

    post {
        always {
            echo 'Performing post-build actions...'
            echo 'Post-build actions completed!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
