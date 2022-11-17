pipeline {
    agent any
    triggers {
        cron('* * * * *')
    }    
    environment {
        BUILD_ID=007
        AUTHOR="Emre Coskun"
        SOFTWARE_VERSION="0.0.1"    
    }
    stages {
        stage('Build') {
            steps {
                echo " Die BuildID lautet: ${BUILD_ID}  Jobname ist: ${JOB_NAME}  Build mit der Nummer ${BUILD_NUMBER} wird gebaut  Diese pipline wurde erstellt von ${AUTHOR} und ist die Software Version ${SOFTWARE_VERSION}"
                bat '''
                mvn package
                cd target
                dir
                '''
               archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                  
            }
        }


 
    }
}