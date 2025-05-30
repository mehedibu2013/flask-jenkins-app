pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t flask-jenkins-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                bat 'docker stop flask-app || exit /b 0'
                bat 'docker rm flask-app || exit /b 0'
                bat 'docker run -d -p 5000:5000 --name flask-app flask-jenkins-app'
            }
        }
    }
    post {
        success {
            echo 'Flask app deployed successfully! Access it at http://localhost:5000'
        }
        failure {
            echo 'Deployment failed! Check the console output for details.'
        }
    }
}