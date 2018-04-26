pipeline {
  agent any
  stages {
    stage('Package') {
      steps {
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn clean package'''
        archiveArtifacts(artifacts: '**/*.war', onlyIfSuccessful: true)
      }
    }
    stage('Deploy-Staging') {
      steps {
        copyArtifacts(projectName: 'Package', filter: '**/*.war')
      }
    }
  }
  environment {
    M2_HOME = '/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn'
  }
}