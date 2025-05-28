
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/prathamesh16013/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
