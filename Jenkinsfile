@Library("shared-library@DevOps") _

pipeline {
    agent {label 'dev-server'}

    stages {
        stage('Checkout code') {
            steps {
                codeCheckout('DevOps', 'https://github.com/Danish-0710/Springboot-Bank-App.git')
            }
        }
        stage('build') {
            steps {
                buildImage("springboot-application")
            }
        }
        stage('Push Image') {
            steps {
                pushImage("springboot-application")
            }
        }
        stage('Deploy'){
            steps{
                deploy()
            }
        }
        
    }
}

