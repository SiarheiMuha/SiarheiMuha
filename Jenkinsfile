node {
  stage('SCM') {
    checkout scm
  }
  stage("LS") {
    sh "ls -ltrR4 /"
  }
  stage('SonarQube Analysis') {
   def scannerHome = tool name: 'sonarqube_dev', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
    withSonarQubeEnv('sonarqube_dev') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
