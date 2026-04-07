pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ecommerce-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop ecommerce-container-jenkins || true'
                sh 'docker rm ecommerce-container-jenkins || true'
                sh 'docker run -d --name ecommerce-container-jenkins -p 3001:80 ecommerce-site'
            }
        }

    }
}