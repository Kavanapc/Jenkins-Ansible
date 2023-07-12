pipeline {
    agent any

    stages {
        stage('code') {
            steps {
               git url:"https://github.com/Kavanapc/Jenkins-Ansible.git" , branch: "master"
            }
        }
    
        stage('deployment through ansible'){
            steps{
                sh "chmod 400 ansible.pem"
              ansiblePlaybook becomeUser: 'ubuntu', credentialsId: 'ansible_ssh_connection', disableHostKeyChecking: true, inventory: '/etc/ansible/hosts', playbook: 'nginx_play.yml'
            }
        }
    }
    
}

