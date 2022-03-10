pipeline {
    environment {
      BRANCH_NAME="main"
    }
    def triggers = []
      if("$BRANCH_NAME" == 'main') {
        triggers << cron('42 11 * * *') // every 15 minutes
    } else if("$BRANCH_NAME" == 'release') {
       triggers << cron('34 12 * * *') // daily between midnight & 2 AM
    } else {
    // no scheduled build
    }
properties (
    [
        pipelineTriggers(triggers)
    ]
)
    agent any
    stages {
        stage('Etapa 1 establemcemos parametros') {
            steps {
                echo 'Hello World'
                script{ 
                properties([parameters([
                    string(description: 'Debe suministrar el UDID del iphone que se dejara enchufado para compilaciones y test', name: 'UDID')])])
                } 
            }
        }
        stage('Etapa 2'){
            steps {
                echo 'Etapa 21'
                echo "el dispositivo es: $params.UDID"
            }
        }
        
    }
    post{
          always {
        echo 'limpio Workspace para la proxima'
        cleanWs()
          }
    }
}
