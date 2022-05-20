pipeline {
    agent any
    environment:
        maven= /usr/share/maven
    tools {
        maven "maven3.6.3"
    }
    stages{
        stage('Build'){
            steps{
                 sh script: 'mvn clean package'
            }
        }
    }
}    
    
