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
                    sh 'docker build -t cyclewebpage:2 . -f html/Dockerfile'
                }
            }
        }
        stage('Create Container') {
            steps {
                script {
                    sh 'docker run -itd --name cycleCont2 -p 9092:80 cyclewebpage:1'
                }
            }
        }
    }
}

