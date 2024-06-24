pipeline{
  agent any
    tools{
      jdk 'jdk17'
      nodejs 'node18'
    }
  environment{
    SONAR_HOME=tool 'sonarqube'
  }
  stages{
    stage("Clean Workspace"){
      steps{
        cleanWs()
      }
    }
    stage("Git checkout"){
      steps{
        git branch: 'main', url: 'https://github.com/Yatingambhir85/Portfolio'
      }
    }
    stage("Sonar analysis"){
      steps{
        withSonarQubeEnv('sonarqube'){
          sh ' $SONAR_HOME/bin/sonar-scanner -Dsonar.projectName=practice-portfolio -Dsonar.projectKey=practice-portfolio'
        }
      }
    }
  }
}
    
    
