pipeline {
    agent any
    stages {
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarScanner' // Use the SonarScanner tool defined in Jenkins global tools
                    withSonarQubeEnv('sonar_qube_no_token') { // No need to specify server name if only one SonarQube instance is configured
                        bat "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
