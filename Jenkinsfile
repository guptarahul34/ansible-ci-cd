pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                sh "ansible all -m ping -i hosts"
            }
        }        
    }
}
