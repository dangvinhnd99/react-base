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
                sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55 "cd /var/www/react-base/html/react-base && ls"'
            }
        }
        stage('git'){
            steps{
                git 'git clone https://github.com/dangvinhnd99/react-base.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Build project') {
            steps {
                sh 'yarn run build'
            }
        }
    }
}
