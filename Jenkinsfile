pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                sh 'whoami'
                sh "sudo ansible all -m ping -i hosts -u rahul"
            }
        }        
    }
}
