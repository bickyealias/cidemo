pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh '''echo PATH = ${PATH}
e ho M2HOME = ${M2HOME}
mvn clean'''
      }
    }
  }
}