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
        stage('change dir'){
            steps {
                 sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "cd /var/www/react-base/html/react-base && ls"'
                 }
            }
        }
        stage('git pull'){
            steps{
                sshagent(['vinhssh']) {
                 sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "sudo git pull origin master"'
                }
            }
        }
     
        stage('Install dependencies') {
            steps {
                sshagent(['vinhssh']) {
                     sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "sudo yarn install"'
                }
            }
        }
        stage('Build project') {
            steps {
                sshagent(['vinhssh']) {
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "yarn run build"'
                }
            }
        }
    }
}
