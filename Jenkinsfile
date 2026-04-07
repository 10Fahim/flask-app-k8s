pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'git@github.com:10Fahim/flask-app-k8s.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
