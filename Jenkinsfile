pipeline {
    agent any
    stages {
        stage('ssh'){
            step {
                sh 'ssh -i sshkey.pem ubuntu@54.172.24.178'
            }
        }
        stage('change dir'){
            sh 'cd /var/www/react-base/html/react-base'
        }
        stage('git'){
            git 'git clone https://github.com/dangvinhnd99/react-base.git'
        }
        stage('Install dependencies') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Build projectasdasdsa') {
            steps {
                sh 'yarn run build'
            }
        }
    }
}


// pipeline {
//     agent any
//     stages {
//         stage('Clone'){
//             step {
//                 git 'https://github.com/dangvinhnd99/jenkins-github.git'
//             }
//         }
//     }
// }
