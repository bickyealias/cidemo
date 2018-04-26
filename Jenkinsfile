pipeline {
  agent any
  stages {
    stage('Package') {
      parallel {
        stage('Package') {
          steps {
            sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn clean package'''
            archiveArtifacts(artifacts: '**/*.war', onlyIfSuccessful: true)
          }
        }
        stage('StaticAnalysis') {
          steps {
            checkstyle(canRunOnFailed: true)
          }
        }
      }
    }
    stage('Deploy-Staging') {
      parallel {
        stage('Deploy-Staging') {
          steps {
            copyArtifacts(projectName: 'Package', filter: '**/*.war')
          }
        }
        stage('Install') {
          steps {
            sh '''set +x
echo "Deploying to Tomcat at http://tomcat:8080/myapp"
curl -s --upload-file webapp/target/webapp.war "http://admin1:bicky1122@localhost:8090/manager/text/deploy?path=/webapp&update=true&tag=${BUILD_TAG}"'''
          }
        }
      }
    }
  }
  environment {
    M2_HOME = '/Users/bickyealias/Downloads/apache-maven-3.5.3/bin/mvn'
  }
}