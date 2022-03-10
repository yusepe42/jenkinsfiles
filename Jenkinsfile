/* programador de ejecucion cada 1 minuto , tiene que ejecutarse 1 vez para que se aplique el cambio
def triggers = []
if ("$BRANCH_NAME" == 'main') {
    triggers << cron('* * * * *')

properties (
    [
        pipelineTriggers(triggers)
    ]
)*/
pipeline {
    environment {
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
