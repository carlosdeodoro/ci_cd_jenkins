pipeline {
    agent any

    tools {
        nodejs 'nodejs'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies'
                bat 'npm install'
            }
        }
        stage('Run Cypress Tests') {
            steps {
                echo 'Running Cypress tests'
                bat 'npm test'
            }
        }
    }
    post {
        success {
            echo 'Cypress tests completed successfully.'
        }
        failure {
            echo 'Cypress tests failed.'
        }
    }
}