pipeline {
    agent any

    stages {
        stage('Stage1') {
            steps {
                echo 'Hello World from A'
            }
        }
        stage('Stage2') {
            steps {
                echo 'Hello World from A'
            }
        }
    }
 post{
     success{
         build job: 'B'
     }
 }
}
