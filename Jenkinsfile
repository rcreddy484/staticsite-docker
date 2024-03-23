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
                    sh 'docker build -t cyclewebpage:1 . -f html/Dockerfile'
                }
            }
        }
        stage('Create Container') {
            steps {
                script {
                    sh 'docker run -itd --name cycleCont1 -p 9091:80 cyclewebpage:1'
                }
            }
        }
    }
}

