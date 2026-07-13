pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Repository cloned by Jenkins'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t simple-app:v1 .'
            }
        }

        stage('List Docker Images') {
            steps {
                sh 'docker images'
            }
        }
        stage('Build Docker Image') {
            steps {
               sh 'docker build -t docker-pipeline:v1 .'
                }
       }
        stage('Run Docker Container') {
           steps {
               sh '''
                docker rm -f docker-container || true
                docker run -d --name docker-container -p 8081:80 docker-pipeline:v1
                '''
                }
        }
    }
}
