pipeline {
       agent any
       stages {
                stage("Cleaning Stage") {
                  steps {
                            bat "call mvn clean "
                        }
                  }
                  
                   stage("upload war to nexus3") {
                  steps {
                      nexusArtifactUploader artifacts: [
                        [
                             artifactId: 'jenkins',
                             classifier: 'war',
                             file: 'target/jenkins-app-0.0.1.war',
                             type: 'war'
                        ]
                     ], 
                     credentialsId: 'NEXUS_CRED',
                     groupId: 'com.maven.demo', 
                     nexusUrl: 'localhost:8110',
                     nexusVersion: 'nexus3', 
                     protocol: 'http', repository: 'http://localhost:8110/repository/maven-central-repository/', 
                     version: '0.0.1'
                        }
                   }
                }
       }

          
      
