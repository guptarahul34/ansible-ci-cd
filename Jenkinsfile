pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                sh 'whoami'
                sh "ansible all -m ping -i hosts -u rahul"
            }
        }        
    }
}
