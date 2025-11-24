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
        ##

        
