pipeline {
  agent any
  stages {
    stage('Inicio') {
      steps {
        echo 'Inicio modificado'
      }
    }
    stage('Build && SonarQube analysis') {
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
        sleep 5
        timeout(time: 1, unit: 'HOURS') {
	  waitForQualityGate abortPipeline: true
	}
      }
    }	
    stage('Test') {
      steps {
	dir('example') {
          sh 'mvn clean test'
	}
      }
    }
    stage('Fin') {
      steps {
        echo 'Finalizar'
      }
    }
  }
}
