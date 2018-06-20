pipeline {
  agent any
  stages {
    stage('Inicio') {
      steps {
        echo 'Inicio modificado'
      }
    }
    stage('SonarQube analysis') {
      withSonarQubeEnv('My SonarQube Server') {
        sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:RELEASE:sonar'
      }
    }	
    stage('Test') {
      steps {
        echo 'Tests'
      }
    }
    stage('Fin') {
      steps {
        echo 'Finalizar'
      }
    }
  }
}
