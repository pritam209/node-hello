 pipeline {
    agent any
    stages {
        stage('gitclone') {
            steps { 
                sh'''npm i'''
                sh'''npm run build'''
            }
        }
        stage('Deploy') {
            steps{
              sshagent(credentials : ['barath']) {
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@3.20.203.66'
              sh 'scp -p -r /var/lib/jenkins/workspace/my-work@2 ubuntu@3.20.203.66:/var/www/html'
              }
            }
        }
    }
}