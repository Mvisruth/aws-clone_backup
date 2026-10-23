
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify Docker') {
            steps {
                sh 'docker version'
            }
        }

        stage('Build Application') {
            steps {
                sh 'docker build -t aws-clone:latest -f Dockerfile .'
            }
        }

        stage('Verify Image') {
            steps {
                sh 'docker image inspect aws-clone:latest'
            }
        }
    }

    post {
        success {
            echo 'Application Docker image built successfully!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output for details.'
        }
    }
}
