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
                bat 'npm install'  // Changed from 'sh' to 'bat'
            }
        }
        
        stage('Run Tests') {
            steps {
                bat 'npm test'  // Changed from 'sh' to 'bat'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t todo-app .'  // Changed from 'sh' to 'bat'
            }
        }
    }
}