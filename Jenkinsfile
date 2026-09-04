pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-project .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f my-container || true'
                sh 'docker run -d --name my-container my-project'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
