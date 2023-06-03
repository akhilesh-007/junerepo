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
    }
}
