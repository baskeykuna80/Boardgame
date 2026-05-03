pipeline {
    agent {label 'slave1'}
    tools{
        maven 'maven3.9'
        jdk 'jdk17'
    }
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jaiswaladi246/Boardgame.git'
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Completed Project') {
            steps {
                echo "Execution has been completed , Please check"
            }
        }
    }
}

