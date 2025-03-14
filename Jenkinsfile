pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                sh 'su - rahul'
                sh "ansible all -m ping -i hosts"
            }
        }        
    }
}
