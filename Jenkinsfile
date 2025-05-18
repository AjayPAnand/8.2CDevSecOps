pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AjayPAnand/8.2CDevSecOps.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install || exit /b 0'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npm test || true'
            }
        }
        stage('Generate Coverage Report') {
            steps {
                bat 'npm run coverage || true'
            }
        }
        stage('NPM Audit (Security Scan)') {
            steps {
                bat 'npm audit || true'
            }
        }
    }
}
