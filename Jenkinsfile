pipeline {
    agent { any }
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
            input message: 'Finished ? (Click "Proceed" to continue)'
            sh './scripts/kill.sh'
          }
        }
    }
}