pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                ansiColor('xterm') {
                    sh "ansible-playbook git_install.yml -i hosts"
                }
            }
        }        
    }
}
