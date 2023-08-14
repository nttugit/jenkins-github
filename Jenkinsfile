pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nttugit/jenkins-github.git'
            }
        }
        stage('Build and Push Docker Image') {
            steps {
                    withDockerRegistry(credentialsId: 'nicenguyen-docker-hub', toolName: 'jenkins-docker', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t nicenguyen/jenkins-github:v2'
                    sh 'docker push nicenguyen/jenkins-github:v2'
                    }
            }
        }
    }
}
