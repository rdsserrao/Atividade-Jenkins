pipeline {
    agent any
            parameters {
                string(name: 'IMAGEM', defaultValue: 'jenkins1', description: 'Nome da imagem')
                string(name: 'CONTENTOR', defaultValue: 'cont1', description: 'Nome do contentor')
                string(name: 'PORTA', defaultValue: '3000', description: 'Número da porta')
            }

            stages {
                stage('Clean') {
                    agent any
                    steps {
                        cleanWs()
                    }
                }
                stage ('Criar Imagem') {
                    agent any
                    steps {
                        sh 'docker build -t "${IMAGEM}​​" .'
                    }   
                } 
                stage ('Criar Contentor') {
                    agent any
                    steps {
                        sh 'docker run -p "${PORTA}​​":3000 -d --name "${CONTENTOR}​​" "${IMAGEM}​​"'
                    }   
                }
            }
}