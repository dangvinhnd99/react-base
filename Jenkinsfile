pipeline {
    agent any
    stages {
           stage('ssh'){
            steps {
//                 sh 'ssh -i /var/lib/jenkins/workspace/pipeline/sshkey.pem ubuntu@54.172.24.178'
               sshagent(['vinhssh']) {
    sh 'ssh -o StrictHostKeyChecking=no -l ubuntu ubuntu@54.152.4.55'
}
    
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
