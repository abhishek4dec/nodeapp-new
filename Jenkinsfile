pipeline {
    agent { 
        any {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    
       
     stages {
        
    stage('CheckOut') {
           steps {
                git 'https://github.com/abhishek4dec/nodeapp-new.git'
            }
        }
        stage('Build') {
            steps {
                echo "bhishek Build Step"
                sh 'npm install'
            }
        }
     }    
}
