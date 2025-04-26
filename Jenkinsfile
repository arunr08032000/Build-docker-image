pipeline {
    agent any

    environment {
      DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
    } 
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t arunr08032000/alpine:latest .'
            }
        }
    }
}
