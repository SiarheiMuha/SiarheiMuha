node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
   def scannerHome = tool 'sonarqube_dev', type: 'hudson.plugins.sonar.SonarRunnerInstallation';
    withSonarQubeEnv('sonarqube_dev') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
