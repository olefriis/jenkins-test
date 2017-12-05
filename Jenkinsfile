pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'make'
        git(url: 'git@github.com:christoflemke/build-test.git', branch: 'master', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
      }
    }
    stage('Test') {
      steps {
        sh 'make check'
        junit 'reports/**/*.xml'
      }
    }
    stage('Deploy') {
      steps {
        sh 'make publish'
      }
    }
  }
}