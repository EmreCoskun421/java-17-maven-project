pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
        cron('@midnight')
    }    
    environment {
        BUILD_ID=007
        AUTHOR="Emre Coskun"
        SOFTWARE_VERSION="0.0.1"    
    }
    stages {

        stage('Build') {
            when {
                allOf {
                    triggeredBy "SCMTrigger"
                    expression {
                        return env.GIT_BRANCH=="origin/main"
                    }
                    
                    
                    
                }
            }                  
        
            steps {
                echo " Die BuildID lautet: ${BUILD_ID}  Jobname ist: ${JOB_NAME}  Build mit der Nummer ${BUILD_NUMBER} wird gebaut  Diese pipline wurde erstellt von ${AUTHOR} und ist die Software Version ${SOFTWARE_VERSION}  branch name ist: ${GIT_BRANCH}"
                bat '''
                git branch
                mvn package
                cd target
                dir 
                '''
               archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                  
            }
        }

        stage('Build2') {
            when {
                 anyOf {
                    triggeredBy "TimerTrigger"
                    expression {
                        return env.GIT_BRANCH=="origin/main"
                    }
                    
                    
                    
                }
            }                
            steps {
                echo " Die BuildID lautet: ${BUILD_ID}  Jobname ist: ${JOB_NAME}  Build mit der Nummer ${BUILD_NUMBER} wird gebaut  Diese pipline wurde erstellt von ${AUTHOR} und ist die Software Version ${SOFTWARE_VERSION}  branch name ist: ${GIT_BRANCH}"
                bat '''
                git branch
                mvn package
                cd target
                dir 
                '''
               archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                  
            }
        }
 
    }
}