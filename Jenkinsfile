pipeline {
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
                npm run test
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                npm run Build
            }
        }
    }
}