
node {
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        git 'https://github.com/LavinaBairagi/jenkins.git'
        
    }
   stage('ansible-deploy'){
        
ansiblePlaybook(credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'inventory.inv', playbook: 'download.yml')    
   }
}
