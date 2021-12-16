pipeline {
    agent any

    stages {
        stage('Etapa 1') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Etapa 2'){
            steps {
                echo 'Etapa 2'
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
