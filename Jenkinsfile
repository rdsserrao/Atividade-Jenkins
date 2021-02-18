pipeline {
    agent any
            parameters {
        string(name: 'Imagem', defaultValue: 'Jenkins1', description: 'Nome da imagem')
        string(name: 'Contentor', defaultValue: 'Cont1', description: 'Nome do contentor')
        string(name: 'Porta', defaultValue: '8000', description: 'Número da porta')
            }

    stages {
        stage ('Criar Imagem') {
            agent {
                docker {
                        image params.Imagem
                }   
            } 
        }
    }
}