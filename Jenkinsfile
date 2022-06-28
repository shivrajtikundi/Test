pipeline {
    environment {
        registry = "write docker hub regestry here}
        regestryCredential = 'dockerhub-cred'
    }
   
    agent any

    tools {
        nodejs "node"
    }

    stages {
         
         stage(Install Packages') {
            steps {
                echo "Starting to install npm package"
                sh 'npm install'
                echo "Finished to install npm package"
            }
         }
         stage('Run Unit Test Cases') {
             steps {
                 echo "Starting Unit test cases"
                 sh "npm run test"
                 echo "Finished unit test cases"
             }
         } 

         stage('Build Docker Image And Push') {
             agent {dockerfile true}
             steps {
                 echo "Starting docker build operation"
                 script {
                    app + docker.build regestry + ":$Build_Number"
                    echo"Built docker image $app
                 }
                 }
         }
