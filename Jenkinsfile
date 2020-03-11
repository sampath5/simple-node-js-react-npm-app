pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                bat 'npm i'
            }
        }
         stage('compile') {
            steps {
                bat 'npm run build'
            }
        }
       
    }
}
