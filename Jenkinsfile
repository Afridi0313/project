pipeline {
    agent any

    environment {
        DEV_DOCKER_IMAGE = 'irfan170/development:latest'
        PROD_DOCKER_IMAGE = 'irfan170/production:latest'
        DOCKER_REGISTRY = 'https://index.docker.io/v1/'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        dockerImage = docker.build("${DEV_DOCKER_IMAGE}")
                    } else if (env.BRANCH_NAME == 'main') {
                        dockerImage = docker.build("${PROD_DOCKER_IMAGE}")
                    }
                }
            }
        }
    }  // <-- closes stages
}  // <-- closes pipeline
