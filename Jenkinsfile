pipeline {
    agent any
    
    stages {

        stage('Inicia mensagem manutenção') {
            steps {
                sh '''
                cd $TARGET
                mv app_online.htm app_offline.htm || true
                '''
            }
        }
        
        stage('Valida Source') {
            steps {
                sh '''
                cd $SOURCE
                ls CHAMADOS.dll
                '''
            }
        }
        
        stage('Copia arquivos do SOURCE para TARGET') {
            steps {
                sh 'rsync -uv $SOURCE/* $TARGET/'
                sh 'rsync -uv $SOURCE/wwwroot/Template/* $TARGET/wwwroot/Template'
            }
        }
        
        stage('Remove mensagem manutenção') {
            steps {
                sh '''
                cd $TARGET
                mv app_offline.htm app_online.htm
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Sistema atualizado com sucesso'
        }
    }
}
