pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-project .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'echo -e "admin\\nadmin" | docker run --rm -i my-project'
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