pipeline {
    agent any
            parameters {
        string(name: 'Imagem', defaultValue: 'jenkins1', description: 'Nome da imagem')
        string(name: 'Contentor', defaultValue: 'cont1', description: 'Nome do contentor')
        string(name: 'Porta', defaultValue: '3000', description: 'Número da porta')
            }

    stages {
        stage('Clean') {
            steps {
        cleanWs()
    }
        }
        stage ('Criar Imagem') {
                steps {
                        sh 'docker build -t "${params.Imagem}​​" .'
                }   
            } 
                    stage ('Criar Contentor') {
                steps {
                        sh 'docker run -p "${params.Porta}​​":3000 -d --name "${params.Contentor}​​" "${params.Imagem}​​"'
                }   
            }
        }
    }