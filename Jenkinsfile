pipeline {
    agent any
    tools {
        maven "maven3.6"
    }
    stages {
        stage('get the code') {
            steps {
                git 'https://github.com/devopscode1/mavenproject'
            }
        }
        stage('build') {
            steps {
               sh 'mvn package'
            }
        }
        stage('approval') {
            steps {
                input 'Do you want to deploy to staging env ?' 
            }
            
        }
        stage('deploy') {
            steps {
                sh 'chmod +x deploy.sh'
                sh './deploy.sh'
            }
            
        }
        
    }
}
