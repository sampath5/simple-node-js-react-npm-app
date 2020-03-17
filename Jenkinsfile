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
 
     /* stage('SonarQube analysis') {
      steps {
        script {
          // requires SonarQube Scanner 2.8+
          scannerHome = tool 'sonar-scanner'
        }
        withSonarQubeEnv('sonarqube-server') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }*/
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
