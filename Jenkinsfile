pipeline {
    agent any
    stages {
        stage("Ansible") {
            steps {
                script {
                    set timeout 5
                    spawn su - rahul
                    expect "Password:"
                    send "Admin@123\r"
                    interact
                }
                sh "ansible all -m ping -i hosts"
            }
        }        
    }
}
