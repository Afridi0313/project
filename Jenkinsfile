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
                // Checkout the code from the Git repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        // Build the Docker image for the dev branch
                        dockerImage = docker.build("${DEV_DOCKER_IMAGE}")
                    } else if (env.BRANCH_NAME == 'main') {
                        // Build the Docker image for the main branch
                        dockerImage = docker.build("${PROD_DOCKER_IMAGE}")
                    }
                }
            }
        }
    }

        
