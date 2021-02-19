pipeline {
    agent any
        parameters { 
        string(name: 'DOCKER_IMAGE_NAME', defaultValue: 'nodejs', description: 'Docker Image')
        string(name: 'DOCKER_CONTAINER_NAME', defaultValue: 'nodejs', description: 'Docker Container Name')
        string(name: 'PORTA_NR', defaultValue: '3000', description: 'Número da porta')
    	}
    // Apaga os dados do Workspace usando o plugin Workspace Cleanup Plugin
    stages {
        stage ('CleanResources') {
            agent any
            steps
            {
                cleanWs()
            }
        }
    // Criar a imagem docker
        stage ('Build Docker Image') {
                agent any
                steps {
                        sh 'docker build -t "${DOCKER_IMAGE_NAME}" .'
                }
            }
    // Inicia o container
            stage ('Run Docker Container') {
                agent any
                steps {
                    sh 'docker rm -f "${DOCKER_IMAGE_NAME}"'
                    sh 'docker run -d -p "${PORTA_NR}":3000 --name "${DOCKER_CONTAINER_NAME}" "${DOCKER_IMAGE_NAME}"'
                }
            }
        }
    }