pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/HAVux/Jenkins-github.git'
            }
        }
        stage('Build'){
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t vuhoang26/buildme .'
                    sh 'docker push vuhoang26/buildme'
                }
            }
        }
    }
}