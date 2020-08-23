pipeline {
    agent any

    stages {
		
        stage('Build Discovery Service') {
            steps {
                echo 'Building Discovery Service...'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean install -Dmaven.test.skip=true'
            }
        }
        stage('Build API Gateway') {
            steps {
                echo 'Building API Gateway..'
                bat 'cd "spring-boot+cloud" && cd api-gateway && mvn clean install -Dmaven.test.skip=true'
            }
        }
        stage('Build Car Service') {
            steps {
                echo 'Building Car Service...'
                bat 'cd "spring-boot+cloud" && cd car-service && mvn clean install -Dmaven.test.skip=true'
            }
        }
        stage('Test Discovery Service') {
            steps {
                echo 'Testing Discovery Service...'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean test'
            }
        }
        stage('Test API Gateway') {
            steps {
                echo 'Testing API Gateway..'
                bat 'cd "spring-boot+cloud" && cd api-gateway && mvn clean test'
            }
        }
        stage('Test Car Service') {
            steps {
                echo 'Testing Car Service...'
                bat 'cd "spring-boot+cloud" && cd car-service && mvn clean test'
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