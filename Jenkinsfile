pipeline {
    agent any

    stages {
        stage('Get Source Code') {
            steps {
                git 'https://github.com/rcreddy484/staticsite-docker.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker build -t Cycle:Webpage .
                }
            }
        }
        stage('Create Container') {
            steps {
                script {
                    docker run -itd --name cycleCont -p 9090:80 Cycle:Webpage
                }
            }
        }
    }
}

