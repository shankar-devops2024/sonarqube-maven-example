node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
//    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "/opt/maven/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=NodeJS_Project -Dsonar.token=sqa_f7e409defd5ce51cafafe2bcd658d5ed0b77aaf6"
    }
  }
}
