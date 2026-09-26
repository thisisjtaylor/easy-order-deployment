pipeline {
    agent any

    stages {
stage('Test Backend') {
    steps {
        dir('easy-order-backend') {
            sh 'chmod +x mvnw'
            sh './mvnw test'
        }
    }
}

stage('Build Frontend') {
    steps {
        dir('easy-order-frontend') {
            sh 'npm ci'
            sh 'npm run build'
        }
    }
}
        stage('Environment Check') {
            steps {
                echo 'Easy Order CI/CD Pipeline Started!'

                sh 'git --version'
                sh 'docker --version'
                sh 'docker compose version'
            }
        }

        stage('Checkout Backend') {
            steps {
                dir('easy-order-backend') {
                    git branch: 'master',
                        url: 'https://github.com/thisisjtaylor/easy-order-backend.git'
                }
            }
        }

        stage('Checkout Frontend') {
            steps {
                dir('easy-order-frontend') {
                    git branch: 'main',
                        url: 'https://github.com/thisisjtaylor/easy-order-frontend.git'
                }
            }
        }

        stage('Verify Source Code') {
            steps {
                echo 'Backend files:'
                sh 'ls -la easy-order-backend'

                echo 'Frontend files:'
                sh 'ls -la easy-order-frontend'
            }
        }

    }
}
