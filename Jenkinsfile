pipeline {
  agent any
  stages {
    stage('Checkout Pipeline') {
      parallel {
        stage('Checkout Pipeline') {
          steps {
            ws(dir: 'pipeline') {
              git(url: 'git@github.com:christoflemke/build-test.git', branch: 'pipeline', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
            }
            
          }
        }
        stage('Checkout Frontend') {
          steps {
            ws(dir: 'frontend') {
              git(url: 'git@github.com:christoflemke/build-test.git', branch: 'frontend', changelog: true, credentialsId: 'jenkins-test-repo', poll: true)
            }
            
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
        input(message: 'Hi', id: 'id-hi', ok: 'Ja')
      }
    }
    stage('Done') {
      steps {
        sh 'find .'
      }
    }
  }
}