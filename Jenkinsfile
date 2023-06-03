pipeline {
    agent any
    environment {
    Docker_Image_Name='myimage'
    Docker_Tag='v3'
    }    
    options { 
        timestamps() 
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
    }
    stages {
        stage('pre-check'){
            parallel {
        stage('git') {
            steps { 
            sh 'git --version'
            }
        }
        stage('docker') {
            steps {
                sh 'docker --version'
                sh 'sleep 30'
            }
        }
            }
        }
 stage('docker-build'){
            steps {
                sh "sudo docker build -t ${Docker_Image_Name}:${env.BUILD_NUMBER} ."
                sh "sudo docker inspect ${Docker_Image_Name}:${env.BUILD_NUMBER}"
            }
        }
        stage('docker-image-verify'){
            steps {
                sh 'sudo docker images'
            }
        } 
    }
}
