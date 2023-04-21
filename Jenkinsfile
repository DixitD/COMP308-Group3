pipeline {
    agent any
    tools {
        nodejs "nodejs"
        git "Default"
    }
        
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/parthshah235/COMP308-Group3.git'
            }
        }
        stage('Build') {
          steps {
            bat 'npm install'
          }
        }  
        
       stage('Test') {
          steps {
            echo "Test run successfully!"
          }
        }
        
       stage('Development') {
           steps {
               echo "Deliver started to Dev Env"
               input message: 'Finished using the web site? (Click "Proceed" to continue)' 
           }
        }
        
        stage('QAT') {
            steps {
               echo "Deliver started to QAT Env"
           }
        }
        
        stage('Staging') {
            steps {
               echo "Deploy to Staging Env"
           }
        }
        
        stage('Production') {
            steps {
               echo "Deploy to Production Env"
               input message: 'Finished production stage of web site? (Click "Proceed" to continue)' 
           }
        }
        
    }
}