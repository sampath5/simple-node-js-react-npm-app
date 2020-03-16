pipeline {
    agent any
    environment { 
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
 
      stage('SonarQube analysis') {
        def scannerHome = tool 'sonar-scanner';
        withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
          sh "${sonar-scanner}/bin/sonar-scanner"
        }
       }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
       /* stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }*/
    }
}
