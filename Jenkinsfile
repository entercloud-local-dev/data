pipeline {
  agent {
    docker {
        image 'node:latest'
        args '-p 3000:3000'
    }
  }
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
  }
    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
      } 
    } 
  environment {
    CI = 'true'
  }
}
