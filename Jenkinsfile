
node {
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        git 'https://github.com/LavinaBairagi/jenkins.git'
        
    }
   stage('Ansible'){
        
ansiblePlaybook(credentialsId: 'id_rsa', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'inventory.inv', playbook: 'download.yml')    
   }
}
