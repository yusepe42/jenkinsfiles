pipeline {
    agent any

    stages {
        stage('Etapa 1 establemcemos parametros') {
            steps {
                echo 'Hello World'
                properties([parameters([string(description: 'Debe suministrar el UDID del iphone que se dejara enchufado para compilaciones y test, para consultarlo: Xcode->Window->Devices and Simulators y en el iphone que se usará el cambio Identifier... Pegar en el valor que aparace.', name: 'UDID', trim: true)])])
                
            }
        }
        stage('Etapa 2'){
            steps {
                echo 'Etapa 2'
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
