pipeline {
  agent any
  stages {
    stage('Inicio') {
      steps {
        echo 'Inicio modificado'
      }
    }
    stage('build && SonarQube analysis') {
      steps {
        withMaven(maven:'Maven 3.5') {
          sh 'mvn clean package sonar:sonar'
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
