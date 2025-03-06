pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/buzzaws/Task_4.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("buzzeraws/sample-flaskapp:latest")
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials') {
                        dockerImage.push()
                    }
                }
            }
        }
        stage('Deploy to Container') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials') {
                        dockerImage.run('-p 8000:8000 --name sample-flaskapp')
                    }
                }
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed. Not deploying to container.'
        }
    }
}
