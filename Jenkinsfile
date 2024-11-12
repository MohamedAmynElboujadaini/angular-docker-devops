pipeline {
    agent any 
    stages {
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv('sonar_qube_no_token') {
      bat "${scannerHome}/bin/sonar-scanner"
    }
  }

    }
}
