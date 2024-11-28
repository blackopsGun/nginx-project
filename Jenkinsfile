pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git "https://github.com/blackopsGun/nginx-project.git"
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t blackopsgun/nginx-app:latest .'
            }
        }
        stage('Push Docker Image') {
            steps {
                sh 'docker push blackopsgun/nginx-app:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f kubernetes/'
            }
        }
    }
}
