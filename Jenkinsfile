pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                sh "ansible-playbook git_install.yml -i hosts"
            }
        }        
    }
}
