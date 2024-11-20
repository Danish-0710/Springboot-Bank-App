@Library('Shared')_
pipeline{
    agent { label 'dev-server'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/Danish-0710/Springboot-Bank-App.git","prod")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("bank-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","bank-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
