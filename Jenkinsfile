
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

        stage('Build') {
            steps {
                echo 'GitHub checkout and Docker verification succeeded.'
            }
        }
    }
}
