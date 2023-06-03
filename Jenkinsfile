pipeline {
    agent any
    environment {
    Docker_Image_Name='myimage'
    Docker_Tag='v2'
    }
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
                sh 'sudo docker build -t $Docker_Image_Name:$Docker_Tag .'
            }
        }
        stage('docker-image-verify'){
            steps {
                sh 'sudo docker images'
            }
        } 
    }
}
