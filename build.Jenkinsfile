pipeline {
    agent any

    environment {
        DOCKER_REGISTRY_URL = 'https://hub.docker.com/repository/docker/yuval1911/yuval-docker-repo/general'
        DOCKER_REGISTRY_CREDENTIALS = '1a5229c1-38f5-450c-97f5-e455295eeb84'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Your Docker registry credentials
                    def registryCredentials = 'yuvallebel'
                    // Log in to Docker Hub using withCredentials
                    sh "docker login -u ${env.DOCKER_REGISTRY_USERNAME} -p ${env.DOCKER_REGISTRY_PASSWORD} ${env.DOCKER_REGISTRY_URL}"
                    
                    // Build Docker image
                    sh 'docker build -f /home/yuval1911/PycharmProjects/roberta/Dockerfile -t yuval1911/yuval-docker-repo:roberta .'
                    
                    // Tag Docker image
                    sh 'docker tag yuval1911/yuval-docker-repo:roberta yuval1911/yuval-docker-repo:custom-tag'
                    
                    // Push Docker image
                    sh 'docker push yuval1911/yuval-docker-repo:roberta'
                }
            }
        }
    }
}
