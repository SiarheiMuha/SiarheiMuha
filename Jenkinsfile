node {
  stage('SCM') {
    checkout scm
  }
  stage("LS") {
    sh "ls -ltrR /home/jenkins/agent/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonarqube_dev/bin"
  }
  stage('SonarQube Analysis') {
   def scannerHome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
    withSonarQubeEnv('SonarScanner') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
