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
                    sh "ansible all -m yum -a name=tree -i hosts -b"
                }
            }
        }
    }
    post {
       failure {
           script {
               def buildUrl = "${JENKINS_URL}\n" +
                   "${env.JOB_NAME}\n" +
                   "${env.BUILD_NUMBER}"
               office365ConnectorSend webhookUrl: 'https://v3consultanciescom.webhook.office.com/webhookb2/3d935c06-895c-4777-a9b1-fb7b1dd318c2@f948506a-3b26-456c-a15c-cb5d92e2ae58/IncomingWebhook/c3431004d646471ebbd947aac335b0d1/f4b35d42-940e-469e-8b1d-5fbd8b3d73c1/V2WolEuBNbpE0qycfyfoqLgj7unyilshLSIjIgLJxQv4M1', message: "Build Failed! \n${buildUrl}" 
           }
       }
       success {
           script {
               def buildUrl = "${JENKINS_URL}\n" +
                   "${env.JOB_NAME}\n" +
                   "${env.BUILD_NUMBER}" 
               office365ConnectorSend webhookUrl: 'https://v3consultanciescom.webhook.office.com/webhookb2/3d935c06-895c-4777-a9b1-fb7b1dd318c2@f948506a-3b26-456c-a15c-cb5d92e2ae58/IncomingWebhook/c3431004d646471ebbd947aac335b0d1/f4b35d42-940e-469e-8b1d-5fbd8b3d73c1/V2WolEuBNbpE0qycfyfoqLgj7unyilshLSIjIgLJxQv4M1', message: "Build Succeeded! \n${buildUrl}"
           }
       }
    }
}
