pipeline {
    agent any 
    stages {
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'sonar-scanner' // Use tool defined in Jenkins global tools
                    withSonarQubeEnv("SonarQubeAngular") {
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
              stage('Quality Gate') {
            steps {
                timeout(time: 5, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}
