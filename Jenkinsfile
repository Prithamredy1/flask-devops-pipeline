pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Prithamredy1/flask-devops-pipeline.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-devops-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f flask-app || true'
                sh 'docker run -d -p 5000:5000 --name flask-app flask-devops-app'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds', 
                    usernameVariable: 'DOCKER_USER', 
                    passwordVariable: 'DOCKER_PASS')]) {
                    
                    sh """
                    echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                    docker tag flask-devops-app $DOCKER_USER/flask-devops-app:latest
                    docker push $DOCKER_USER/flask-devops-app:latest
                    """
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline finished."
        }
    }
}
