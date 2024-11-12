pipeline{
  agent any 
  stages{

    
                stage("Test Vulnerabilities With SonarQube") {
            steps {
                script {
                        bat """
                            sonar-scanner.bat -Dsonar.projectKey=angulartest \
                                              -Dsonar.sources=. \
                                              -Dsonar.language=js \
                                              -Dsonar.host.url=http://localhost:9000 \
                                              -Dsonar.token=sqp_f3dfe31a1b6c7c5fce27cf31d011c3b9b2c61d69
                        """
                }
            }
        }


        
    
  }

  
}
