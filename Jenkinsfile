pipeline {
    agent {
        docker {
        image 'node:10.15.2'
        label 'jnode1'
         }
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
            input message: 'Finished ? (Click "Proceed" to continue)'
            sh './scripts/kill.sh'
          }
        }
    }
}