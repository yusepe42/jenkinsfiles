// programador de ejecucion cada 1 minuto , tiene que ejecutarse 1 vez para que se aplique el cambio

def triggers = []
if ("$BRANCH_NAME" == 'WEF-2244') {
    triggers << cron('H 0 * * *')
}
properties (
    [
        pipelineTriggers(triggers)
    ]
)
pipeline {
    agent any
    stages {
        stage('SetupParameters') {
            steps {
                 script {
                    properties([
                      parameters([
                          booleanParam(defaultValue: true, description: '', name: 'DEBUG'),
                          booleanParam(defaultValue: false, description: 'Endpoints', name: 'RELEASE'),
                          booleanParam(defaultValue: true, description: '', name: 'DEVELOPMENT'),
                          booleanParam(defaultValue: false, description: '', name: 'QA'),
                          booleanParam(defaultValue: false, description: '', name: 'PRODUCTION')])])
                  }
            }
         }
        stage('Etapa 1 establemcemos parametros') {
            steps {
                echo 'Hello World'
                // script{ 
                // properties([parameters([
                //     string(description: 'Debe suministrar el UDID del iphone que se dejara enchufado para compilaciones y test', name: 'UDID')])])
                // } 
            }
        }
        stage('Etapa 2'){
            steps {
                echo 'Etapa 2'
               // echo "el dispositivo es: $params.UDID"
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
