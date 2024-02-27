node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
//    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "/opt/maven/bin/mvn sonar:sonar -Dsonar.host.url=http://172.31.6.142:9000 -Dsonar.login=sqa_f7e409defd5ce51cafafe2bcd658d5ed0b77aaf6 -Dsonar.projectKey=NodeJS_Project"
    }
  }
  stage('neomsense-dpcheck') {
      steps {
         dependencyCheck additionalArguments: '--format HTML', odcInstallation: 'neomsense-dpcheck'
    }    
}
}
