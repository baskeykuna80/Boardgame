pipeline {
    agent any
    tools{
        maven 'maven3'
        jdk 'jdk17'
    }
    parameters{
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Git branch to build')
    }
    stages {
        stage('Git Checkout') {
            steps {
                git branch: "${params.BRANCH_NAME}", url: 'https://github.com/baskeykuna80/Boardgame.git'
            }
        }
        stage('BUILD') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
