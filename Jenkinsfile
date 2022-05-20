pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                 sh script: 'mvn clean package'
            }
        }
         stage('Upload war to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'simple-app1',
                        classifier: '',
                        file: 'target/simple-app1-1.0.0.war', 
                        type: 'war'
                        ]
                ], 
                credentialsId: 'nexus3',
                groupId: 'in.javahome',
                nexusUrl: '172.31.5.198', 
                nexusVersion: 'nexus3',
                protocol: 'http', 
                repository: 'http://65.1.94.81:8081/repository/simpleapp-release/', 
                version: '3.0.0'
            }
         }
    }
}
    
