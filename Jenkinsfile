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
                stage('Run Test Suite 1') {
                    steps {
                        echo 'Running Test Suite 1'
                        bat 'npm run test-suite-1'
                    }
                }
                stage('Run Test Suite 2') {
                    steps {
                        echo 'Running Test Suite 2'
                        bat 'npm run test-suite-2'
                    }
                }
                stage('Run Test Suite 3') {
                    steps {
                        echo 'Running Test Suite 3'
                        bat 'npm run test-suite-3'
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