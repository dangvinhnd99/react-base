pipeline {
    agent any
    stages {
        stage('ssh'){
            step {
                sh 'ssh -i sshkey.pem ubuntu@54.172.24.178'
            }
        }
        stage('change dir'){
            dir('/var/www/react-base/html/react-base') {
    // some block
        }
            stage('git'){
            git 'git pull origin master'
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
