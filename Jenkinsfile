pipeline {
    agent any
    stages {
        stage('git') {
            steps { 
            sh 'git --version'
            }
        }
        stage('docker') {
            steps {
                sh 'docker --version'
            }
        }
 stage('docker-build'){
            steps {
                sh 'sudo docker build -t myimage:v1 .'
            }
        }
        stage('docker-image-verify'){
            steps {
                sh 'sudo docker images'
            }
        } 
    }
}
