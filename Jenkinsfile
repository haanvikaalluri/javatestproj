
node {
  agent any

tools{
maven 'maven3.9.6'

}
stage('CheckOutCode'){
    steps{
    git branch: 'main', credentialsId: '128df971-41a6-442a-adc7-46a7e00be359', url: 'https://github.com/haanvikaalluri/maven-web-application.git'
	
	}
  }
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=haanvikaalluri_javatestproj_AY4s53n99NsJu0Dn8kV0"
    }
  }
}
