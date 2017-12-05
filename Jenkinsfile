pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'git@github.com:christoflemke/build-test.git', branch: 'master', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
      }
    }
    stage('Test') {
      steps {
        sh 'git status'
      }
    }
    stage('Deploy') {
      steps {
        sh 'make publish'
      }
    }
  }
}