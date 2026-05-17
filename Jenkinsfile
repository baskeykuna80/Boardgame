pipeline {
    agent any

    tools {
        maven 'maven3'
        jdk 'jdk 17'
    }

    environment {
        SCANNER_HOME = tool 'sonar-scanar'
    }

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/baskeykuna80/Boardgame.git'
            }
        }

        stage('Compilation') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('Testing') {
            steps {
                sh 'mvn test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonar') {

                    sh '''
                    $SCANNER_HOME/bin/sonar-scanner \
                    -Dsonar.projectName=Boardgame \
                    -Dsonar.projectKey=Boardgame \
                    -Dsonar.java.binaries=target
                    '''
                }
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Completed') {
            steps {
                echo 'Completed'
            }
        }
    }
}
