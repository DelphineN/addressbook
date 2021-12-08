pipeline{
  agent any
  environment {
    PATH = "$PATH:/usr/share/maven/bin"
  }
  stages{
    stage('Build'){
      steps{
        sh 'mvn clean package'
            }
         }
    stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonar') {
        sh 'mvn clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'          
    }
        }
        }
       
    }
}
