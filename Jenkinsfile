pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'hello-python:latest'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                script {

                    echo "Skipping dependencies installation (no requirements.txt)"
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {

                    echo "Skipping tests (no tests defined)"
                }
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    sh """
                        docker build -t $DOCKER_IMAGE .
                    """
                }
            }
        }
    }
    post {
        success {
            echo 'Build complete'
        }
        failure {
            echo 'Build failed'
        }
    }
}

