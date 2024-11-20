@Library("shared-library@DevOps") _

pipeline {
    agent { label 'dev-server' }

    stages {
        stage("Code clone") {
            steps {
                sh "whoami"
                // Call the cloneRepo method
                cloneRepo("https://github.com/Danish-0710/Springboot-Bank-App.git", "DevOps")
            }
        }

        stage("Code Build") {
            steps {
                // Call the dockerBuild method
                dockerBuild("springboot-app", "latest", "dockerhubuser")
            }
        }

        stage("Push to DockerHub") {
            steps {
                // Call the dockerPush method
                dockerPush("springboot-app", "latest", "dockerhubuser")
            }
        }
    }
}
