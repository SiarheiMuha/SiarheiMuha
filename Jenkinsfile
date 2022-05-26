node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
   def scannerHome = tool 'SonarScanner 2.13';
    withSonarQubeEnv('sonarqube_dev') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
