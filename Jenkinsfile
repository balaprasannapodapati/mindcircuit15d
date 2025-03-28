pipeline {
    agent any

    stages {
        stage('clone the GitHub code') {
            steps {
                echo 'IN THIS STAGE CODE WILL CLONE'
                git branch: 'main', url: 'https://github.com/balaprasannapodapati/mindcircuit15d.git'
            }
           }
         stage('BUILD THE ARTIFACT') {
            steps {
                echo 'IN THIS STAGE BUILD THE ARTICAT'
               sh 'mvn clean install'
            }

           } 
 stage('DEPLOYN THE ARTICAT') {
            steps {
                echo 'THIS IS DEPLOY STAGE'
        

         deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://ec2-54-234-22-55.compute-1.amazonaws.com:8081/')], contextPath: 'pipeline', war: '**/*.war'
            }
        
         }
       }
    
}
