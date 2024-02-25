node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
//    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "/opt/maven/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=NodeJS_Project"
    }
  }
}
