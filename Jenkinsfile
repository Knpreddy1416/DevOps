pipeline {
    agent any
    tools {
        maven '3.9.0'
    }
    stages{
        stage('Build'){
            steps{
                sh script: 'mvn --version'
            }
        }
        stage('Nexus'){
            steps{
               nexusArtifactUploader artifacts: [
                   [
                       artifactId: 'devops', 
                       classifier: '', 
                       file: '/opt/apache-maven-3.9.0/devops/target.jar', 
                       type: 'jar'
                ]
            ], 
            credentialsId: 'NEXUS_CRED', 
            groupId: 'batch02', 
            nexusUrl: '54.197.201.107:8081', 
            nexusVersion: 'nexus3', 
            protocol: 'http', 
            repository: 'http://54.197.201.107:8081/repository/Ammu_release/', 
            version: '1.0'
        }
    }
}
    
}   
