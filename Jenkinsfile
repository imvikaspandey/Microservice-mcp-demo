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
		
        stage('Deploy Application') {
            steps {
                echo 'Deploying application'
                bat ' cd "spring-boot+cloud" && docker-compose stop && docker-compose up --build -d'
				echo 'Your services will be up in few secs :-)'
            }
        }
    }
}