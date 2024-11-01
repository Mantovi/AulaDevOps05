pipeline {
    agent any
    stages {
        stage('Clonar Repositório') {
            steps {
                git branch: 'main', url: 'git@github.com:Mantovi/AulaDevOps05.git'
            }
        }
        stage('Construir e Subir Contêineres') {
            steps {
                script {
                    // Certifique-se de que o Docker e o Docker Compose estão instalados e configurados para o Jenkins
                    sh 'docker-compose down'
                    sh 'docker-compose up -d --build'
                }
            }
        }
    }
    post {
        always {
            script {
                // Finaliza os contêineres após o pipeline
                sh 'docker-compose down'
            }
        }
    }
}
