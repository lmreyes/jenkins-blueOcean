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
        withSonarQubeEnv('Sonar') {
          dir('example'){
            sh 'mvn clean package sonar:sonar'
          }
        }
      }
    }
    stage('Quality Gate') {
      steps {
        timeout(time: 1, unit: 'HOURS') {
	  waitForQualityGate abortPipeline: true
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
