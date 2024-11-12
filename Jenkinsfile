pipeline {
    agent any 
    stages {
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'sonar-scanner' // Use tool defined in Jenkins global tools
                    withSonarQubeEnv("SonarQube") {
                        bat """
                            "${scannerHome}/bin/sonar-scanner" \
                              -Dsonar.projectKey=angulartest \
                              -Dsonar.sources=. \
                              -Dsonar.host.url=http://localhost:9000 \
                              -Dsonar.token=sqp_ae74c5b128ae98e9dd7fecb542c574372aac744e
                        """
                    }
                }
            }
        }
    }
}
