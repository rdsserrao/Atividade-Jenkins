pipeline {
    agent any
            parameters {
        string defaultValue: 'jenkins1', description: 'Nome da Imagem', name: 'Imagem', trim: true
        string(name: 'Contentor', defaultValue: 'cont1', description: 'Nome do contentor', trim: true)
        string(name: 'Porta', defaultValue: '3000', description: 'Número da porta', trim: true)
            }

    stages {
        stage('Clean') {
            steps {
        cleanWs()
    }
        }
        stage ('Criar Imagem') {
                steps {
                        sh 'docker build -t "${Imagem}​​" .'
                }   
            } 
                    stage ('Criar Contentor') {
                steps {
                        sh 'docker run -p "${Porta}​​":3000 -d --name "${Contentor}​​" "${Imagem}​​"'
                }   
            }
        }
    }