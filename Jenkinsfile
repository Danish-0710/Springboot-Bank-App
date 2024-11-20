@Library("shared-library@DevOps") _

pipeline {
    agent {label 'dev-server'}

        stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/Danish-0710/Springboot-Bank-App.git","DevOps")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("springboot-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","springboot-app","latest")
            }
        }   
    }
}

