# Declarative pipeline
pipeline {
    agent any
    environment {
      DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
    } 
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build -t alpine:latest .'
            }
        }
    }
}
