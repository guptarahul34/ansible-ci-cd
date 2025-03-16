pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                ansiColor('xterm') {
                    sh "ANSIBLE_FORCE_COLOR=1 ansible-playbook git_install.yml -i hosts"
                }
            }
        }        
    }
}
