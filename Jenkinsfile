pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Code retrieved from Git'
            }
        }
        
        stage('Build HelloWorld') {
            steps {
                echo 'Compiling HelloWorld...'
                bat 'javac HelloWorld.java'
                bat 'java HelloWorld'
            }
        }
        
        stage('Build Merci') {
            steps {
                echo 'Compiling Merci...'
                bat 'javac Merci.java'
                bat  'java Merci'
            }
        }
        
        stage('Build DeRien') {
            steps {
                echo 'Compiling DeRien...'
                bat 'javac DeRien.java'
                bat 'java DeRien'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo '✅ All builds succeeded!'
        }
        failure {
            echo '❌ A build failed'
        }
    }
}