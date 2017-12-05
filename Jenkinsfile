pipeline {
  agent any
  stages {
    stage('Checkout Frontend') {
      parallel {
        stage('Checkout Frontend') {
          steps {
            git(url: 'git@github.com:christoflemke/build-test.git', branch: 'master', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
          }
        }
        stage('Checkout Pipeline') {
          steps {
            git(url: 'git@github.com:christoflemke/build-test.git', branch: 'pipeline', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
          }
        }
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'git status'
          }
        }
        stage('status2') {
          steps {
            sh 'git status'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        input(message: 'Hi', id: 'id-hi', ok: 'Ja', submitter: 'me', submitterParameter: 'foo')
      }
    }
  }
}