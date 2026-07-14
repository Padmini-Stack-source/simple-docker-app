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
    
      stage('Run Docker Container') {
    steps {
        sh 'docker rm -f docker-container || true'
        sh 'docker run -d --name docker-container -p 8081:80 simple-app:v1'
    }
}
    }
}
