pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn package'
                bat '''
                cd target
                dir
                '''
            }
        }

 
    }
}