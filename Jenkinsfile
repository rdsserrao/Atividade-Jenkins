pipeline {
    agent any
            parameters {
        string(name: 'Imagem', defaultValue: 'Jenkins1', description: 'Nome da imagem')
        string(name: 'Contentor', defaultValue: 'Cont1', description: 'Nome do contentor')
        string(name: 'Porta', defaultValue: '8000', description: 'Número da porta')
            }

    stages {
        stage('Clean') {
            steps {
        cleanWs()
    }
        }
        stage ('Criar Imagem') {
                steps {
                        sh ' docker build -t jenkins1 .'
                }   
            } 
                    stage ('Criar Contentor') {
                steps {
                        sh ' docker run -p 8000:3000 -d --name cont1 jenkins1'
                }   
            }
        }
    }