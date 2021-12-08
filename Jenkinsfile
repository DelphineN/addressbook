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
        sh "mvn sonar:sonar"          
    }
        }
        }
       
    }
}
