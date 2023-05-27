pipeline {
    agent any
tools {
    sonarQubeScanner 'SonarQube Scanner Name'
}
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
        stage('Sonarqube Verification') {
        steps {
            sh "sonar-scanner \
  -Dsonar.projectKey=labphase \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://172.10.0.140:9000 \
  -Dsonar.login=141610cdfadfe7ec8d3eb001404b32bdeff84af3"
        }}
    }

    post {
        always {
            echo 'Performing post-build actions...'
        }

        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
