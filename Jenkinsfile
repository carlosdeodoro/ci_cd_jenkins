pipeline {
    agent any

    tools {
        nodejs 'nodejs'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run Cypress Tests') {
            steps {
                bat 'npm test'
            }
        }
    }
}