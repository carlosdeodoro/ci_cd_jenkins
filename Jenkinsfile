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
            parallel {
                stage('Run Tests in Chrome') {
                    steps {
                        echo 'Running Cypress tests in Chrome'
                        bat 'npm run test-chrome'
                    }
                }
                stage('Run Tests in Firefox') {
                    steps {
                        echo 'Running Cypress tests in Firefox'
                        bat 'npm run test-firefox'
                    }
                }
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