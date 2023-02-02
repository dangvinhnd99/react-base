pipeline {
    agent any
    stages {
        stage('ssh'){
            step {
                sh 'ssh -i sshkey.pem ubuntu@54.172.24.178'
            }
        }
        stage('change dir'){
            dir('/var/www/react-base/html') {
    // some block
        }
            stage('git'){
            git 'git clone https://github.com/dangvinhnd99/react-base.git'
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
