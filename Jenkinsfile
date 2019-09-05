pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      steps {
        sh '''


npm install -g yarn
npm install yarn

yarn install
yarn upgrade npm install '''
      }
    }
    stage('build2') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh ' ./jenkins/scripts/test.sh'
      }
    }
  }
}