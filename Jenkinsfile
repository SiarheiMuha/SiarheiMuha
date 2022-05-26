node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarqube_dev';
    withSonarQubeEnv(sonarqube_dev) {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
