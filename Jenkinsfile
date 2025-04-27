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
        stage('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-@Arunnura007'
            }
        }
        stage('Tag') {
            steps {
                sh 'docker tag alpine:latest arunr08032000/dockerhub-example:jenkins-project1'
            }
        }
        stage('Push') {
            steps {
                sh 'docker push arunr08032000/dockerhub-example:jenkins-project1'
            }
        }
    }
}
