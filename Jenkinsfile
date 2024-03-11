
node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'maven3.9.6';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=haanvikaalluri_javatestproj_AY4s53n99NsJu0Dn8kV0"
    }
  }
}
