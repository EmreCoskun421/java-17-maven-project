pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo ' Die BuildID lautet: %BUILD_ID%  Jobname ist: %JOB_NAME%  Build mit der Nummer %BUILD_NUMBER% wird gebaut '
                bat '''
                mvn package
                cd target
                dir

                '''

                bat ''
            }
        }


 
    }
}