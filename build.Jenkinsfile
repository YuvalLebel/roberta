pipeline {
    agent any

    environment {

        DOCKER_REGISTRY_PASSWORD = '1a5229c1-38f5-450c-97f5-e455295eeb84'
        DOCKER_REGISTRY_USERNAME = 'yuval1911'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Your Docker registry credentials
                    withCredentials([usernameColonPassword(credentialsId: 'Dockercreds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                        sh '''
                             docker login -u $USERNAME -p $PASSWORD
                        '''
                    }
                    // Log in to Docker Hub using withCredentials

                    
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
