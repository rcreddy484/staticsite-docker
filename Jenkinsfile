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
                    sh 'docker build -t cyclewebpage . -f html/Dockerfile'
                }
            }
        }
        stage('Create Container') {
            steps {
                script {
                    sh 'docker run -itd --name cycleCont -p 9090:80 cyclewebpage'
                }
            }
        }
    }
}

