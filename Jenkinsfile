pipeline {
    node('master')
    agent {
        docker { image 'node:10.15.2' }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm run test'
            }
        }
        stage ('Deliver'){
          steps {
            sh './scripts/deliver.sh'
            input message: 'Finished using the web site? (Click "Proceed" to continue)'
            sh './scripts/kill.sh'
          }
        }
    }
}