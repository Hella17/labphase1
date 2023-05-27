pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the source code...'
               checkout([$class: 'GitSCM', branches: [[name: '*/backend']],
			extensions: [],
			userRemoteConfigs: [[url: 'https://github.com/Hella17/labphase1.git']]])
            }
        }

        stage('Build') {
            steps {
                echo 'Building the backend application...'
        sh "mvn clean install  "
        sh "mvn -B -DskipTests package "
            }
        }
        stage('Sonarqube Verification') {
        steps {
            sh "mvn sonar:sonar \
  -Dsonar.projectKey=labphase \
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
