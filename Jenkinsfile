pipeline {
    agent { 
        any {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    tools {
         nodejs 'nodejs18.7.0'
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
                sh 'npm version'
            }
        }
         stage('Test') {
            steps {
                sh '../jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh '../jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh '../jenkins/scripts/kill.sh'
            }
        }
     }    
}
