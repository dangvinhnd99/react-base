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
                    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "cd /var/www/react-base/html/react-base && sudo git pull origin master && sudo yarn install && sudo yarn run build"'
                 }
            }
        }
    }
}
