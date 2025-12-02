pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        
        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
            post {
                always {
                    // Always continue even if tests fail
                    echo 'Test stage completed'
                }
            }
        }
        
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t todo-app .'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded'
        }
        failure {
            echo 'Pipeline failed'
        }
        always {
            echo 'Pipeline completed'
        }
    }
}