pipeline {
    agent any

    environment {
      DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
    } 
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build -t arunr08032000/alpine:latest .'
            }
        }
        stage('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-@Arunnura007'
            }
        }
        stage('Push') {
            steps {
                sh 'docker push arunr08032000/alpine:latest'
            }
        }
     Post {
       always {
         sh 'docker logout'
       }
    }
}
