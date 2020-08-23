pipeline {
    agent any

    stages {
		
        stage('Build Discovery Service') {
            steps {
                echo 'Building Discovery Service...'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean install'
            }
        }
        stage('Build API Gateway') {
            steps {
                echo 'Building API Gateway..'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean install'
            }
        }
        stage('Build Car Service') {
            steps {
                echo 'Building Car Service...'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean install'
            }
        }
        
        stage('Deploy Application') {
            steps {
                echo 'Deploying application'
                // bat 'docker-compose up --build -d'
            }
        }
    }
}