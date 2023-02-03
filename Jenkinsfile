pipeline {
    agent any
    stages {
        stage('ssh'){
            steps {
                sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55'
                }
            }
        }
        stage('build web nginx'){
            steps {
                 sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "cd /var/www/react-base/html/react-base && sudo git pull origin master && sudo yarn install && sudo yarn run build"'
                 }
            }
        }
        stage('CI terraform'){
            steps {
                 sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "sudo git clone https://github.com/dangvinhnd99/B1.git"'
                 }
            }
        }
         stage('CI terraform 2'){
            steps {
                 sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "cd .B1 && terraform init && terraform apply -auto-approve"'
                 }
            }
        }
    }
}
