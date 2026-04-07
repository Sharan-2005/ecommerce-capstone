pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Sharan-2005/ecommerce-capstone.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ecommerce-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop ecommerce-container || true'
                sh 'docker rm ecommerce-container || true'
                sh 'docker run -d --name ecommerce-container -p 8080:80 ecommerce-site'
            }
        }
    }
}