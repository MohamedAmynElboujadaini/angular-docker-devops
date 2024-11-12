pipeline{
  agent any 
  stages{
      stage('SonarQube Analysis') {
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv("SonarQube") {
      bat  "${scannerHome}/bin/sonar-scanner -D"sonar.projectKey=angulartest" -D"sonar.sources=." -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqp_ae74c5b128ae98e9dd7fecb542c574372aac744e" "
    }
  }


        
    
  }

  
}
