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
  environment {
    M2_HOME = '/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn'
  }
}