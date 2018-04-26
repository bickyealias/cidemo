pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh '''echo PATH = ${PATH}
echo M2HOME = ${M2HOME}
mvn clean'''
      }
    }
  }
}