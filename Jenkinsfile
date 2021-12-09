
node {
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        git 'https://github.com/LavinaBairagi/jenkins.git'
        
    }
    stage('Build') {
                bat "mvn clean test"
    }
    
    stage('Package') {
                bat "mvn package"
    }
    
    stage('ansible-deploy'){
        
       ansiblePlaybook( credentialsId: 'project-key', disableHostKeyChecking: true, installation: 'ansible', inventory: 'inventory.inv', playbook: 'download.yml')
    }
    
    stage('Nexus') {
       nexusArtifactUploader artifacts: [[artifactId: 'jenkins',
 classifier: '', file: 'target/jenkins-0.0.1-SNAPSHOT.jar',
 type: 'jar']], credentialsId: 'nexus', groupId: 'com.maven.demo', 
nexusUrl: 'localhost:8110', nexusVersion: 'nexus3',
 protocol: 'http', 
repository: 'http://localhost:8110/repository/maven-central-repository/',
 version: '0.0.1'    }
}
