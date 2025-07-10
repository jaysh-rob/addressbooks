pipeline {
    agent {label 'prod'}

tools {
  maven 'maven3'
  jdk 'jdk17'
}

    stages {
        stage('Git Checkout') {
            steps {
                echo '==============================================Git Checkout========================================='
                git branch: 'prod', url: 'https://github.com/jaysh-rob/addressbooks.git'
            }
        }
        
        stage('Compile') {
            steps {
                echo '==============================================Compile========================================='
                sh 'mvn compile'
            }
        }
        
        stage('Test') {
            steps {
                echo '==============================================Test========================================='
                sh 'mvn test'
            }
        }
        
        stage('Package') {
            steps {
                echo '==============================================Package========================================='
                sh 'mvn package'
            }
        }
    }
}

