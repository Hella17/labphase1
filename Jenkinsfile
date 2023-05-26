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
