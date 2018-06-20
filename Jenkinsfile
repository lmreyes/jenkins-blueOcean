pipeline {
  agent any
  stages {
    stage('Inicio') {
      steps {
        echo 'Inicio modificado'
      }
    }
    stage('SonarQube analysis') {
      steps {
        withMaven('build && SonarQube analysis') {
         sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:RELEASE:sonar'
        }
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
