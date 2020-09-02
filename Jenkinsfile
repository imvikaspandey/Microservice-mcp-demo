pipeline {
    agent any

    stages {
	
        stage('Build Discovery Service') {
            steps {
                echo 'Building Discovery Service...'
                bat 'cd "spring-boot+cloud" && cd discovery-service && mvn clean install -Dmaven.test.skip=true'
				bat 'cd "spring-boot+cloud" && cd discovery-service && docker build -t discoveryser .'
				bat 'cd "spring-boot+cloud" && cd discovery-service && docker tag discoveryser:latest vkpdocker/micro_cred_discovery:latest'
				bat 'docker login --username=%DOCKER_HUB_USER% --password=%DOCKER_HUB_PASS% && docker push vkpdocker/micro_cred_discovery:latest'
            }
        }
        stage('Build API Gateway') {
            steps {
                echo 'Building API Gateway..'
                bat 'cd "spring-boot+cloud" && cd api-gateway && mvn clean install -Dmaven.test.skip=true'
				bat 'cd "spring-boot+cloud" && cd api-gateway && docker build -t apigateway .'
				bat 'cd "spring-boot+cloud" && cd api-gateway && docker tag apigateway:latest vkpdocker/micro_cred_apigateway:latest'
				bat 'docker login --username=%DOCKER_HUB_USER% --password=%DOCKER_HUB_PASS% && docker push vkpdocker/micro_cred_apigateway:latest'
            }
        }
        stage('Build Car Service') {
            steps {
                echo 'Building Car Service...'
                bat 'cd "spring-boot+cloud" && cd car-service && mvn clean install -Dmaven.test.skip=true'
				bat 'cd "spring-boot+cloud" && cd car-service && docker build -t carservice .'
				bat 'cd "spring-boot+cloud" && cd car-service && docker tag carservice:latest vkpdocker/micro_cred_carservice:latest'
				bat 'docker login --username=%DOCKER_HUB_USER% --password=%DOCKER_HUB_PASS% && docker push vkpdocker/micro_cred_carservice:latest'
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