pipeline {
  agent any
  stages {
    stage('CLONE') {
      steps {
        git(url: 'https://github.com/carreerit/mavenrepo.git', branch: 'master', poll: true)
      }
    }
    stage('MAVEN') {
      steps {
        parallel(
          "MAVEN": {
            sh 'mvn clean'
            
          },
          "COMPILE": {
            sh 'mvn compile'
            
          },
          "package": {
            sh 'mvn package'
            
          }
        )
      }
    }
  }
}