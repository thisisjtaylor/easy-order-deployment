pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'Easy Order CI/CD Pipeline Started!'
            }
        }

        stage('Environment Check') {
            steps {
                sh 'git --version'
                sh 'docker --version'
                sh 'docker compose version'
            }
        }

    }
}