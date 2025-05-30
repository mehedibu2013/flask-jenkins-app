pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/mehedibu2013/flask-jenkins-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-jenkins-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker stop flask-app || true'
                sh 'docker rm flask-app || true'
                sh 'docker run -d -p 5000:5000 --name flask-app flask-jenkins-app'
            }
        }
    }
    post {
        success {
            echo 'Flask app deployed successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
