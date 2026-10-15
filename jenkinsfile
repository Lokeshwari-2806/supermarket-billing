pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Validate Files') {
            steps {
                script {
                    if (!fileExists('index.html')) {
                        error('index.html not found in repository root')
                    }
                }
                echo 'Supermarket Billing System files found!'
            }
        }

        stage('Build') {
            steps {
                echo 'Supermarket Billing System build completed.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
