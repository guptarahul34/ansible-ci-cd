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

        stage("Install Tree Package") {
            steps {
                ansiColor('xterm') {
                    sh "ansible all -m yum -a name=tree"
                }
            }
        }
        
    }
}
