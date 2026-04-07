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
                sh 'docker stop ecommerce-container || true'
                sh 'docker rm ecommerce-container || true'
                sh 'docker run -d --name ecommerce-container -p 3001:80 ecommerce-site'
            }
        }

    }
}