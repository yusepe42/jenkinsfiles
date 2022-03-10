pipeline {
    def triggers = []
      if("env.BRANCH_NAME" == 'main') {
        triggers << cron('12 15 * * *') // every 15 minutes
    } else if("env.BRANCH_NAME" == 'release') {
       triggers << cron('12 18 * * *') // daily between midnight & 2 AM
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
