pipeline {
    agent any
    stages {
          stage('change direct'){
            steps {
            sh 'cd' 
            }
          }
        stage('ssh'){
            steps {
                sh 'ssh -i sshkey.pem ubuntu@54.172.24.178'
            }
        }
        stage('change dir'){
            steps {
            sh 'cd /var/www/react-base/html/react-base' 
            }
    // some block
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
            stage('Build projecdasdsa') {
            steps {
                sh 'yarn run build'
            }
    }
}
    }
