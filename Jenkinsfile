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
                sh 'pip install -r requirements.txt'
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
    }

    post {
        always {
            echo "Pipeline finished."
        }
    }
}
