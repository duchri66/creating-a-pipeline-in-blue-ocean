pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'npm install --no-optional'
          }
        }
        stage('test') {
          environment {
            CI = 'true'
          }
          steps {
            sh ' ./jenkins/scripts/test.sh'
          }
        }
      }
    }
  }
}