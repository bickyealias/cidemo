pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn clean package'''
        archiveArtifacts(artifacts: '**/*.war', onlyIfSuccessful: true)
      }
    }
  }
  environment {
    M2_HOME = '/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn'
  }
}