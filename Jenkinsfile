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
    }
}