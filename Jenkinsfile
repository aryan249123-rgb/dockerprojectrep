pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "devopdemo/html-demo"
    }

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/aryan249123-rgb/dockerprojectrep.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %DOCKER_IMAGE% .'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                bat 'docker login -u devopdemo -p Concealed'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                bat 'docker push %DOCKER_IMAGE%'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }
    }
}