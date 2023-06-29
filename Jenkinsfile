pipeline {
    
    agent any

    environment {
        DOCKER_CRED = credentails('docker')
        REPO = 'moshab679/docker04'
        TAG = 'shahab'
    }

    stages {
        
        stage('Docker build'){
            steps{
                sh 'docker build -t $REPO:$TAG .'
            }
        }

        stage('Docker push'){
            steps{
                sh 'echo $DOCKER_CRED_PSW | docker login -u $DOCKER_CRED_USR --password-stdin'
                sh 'docker push $REPO:$TAG'
            }
        }
    }
}