pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Login to Docker registry
                    sh 'docker login yuval1911/yuval-docker-repo'
                    
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
