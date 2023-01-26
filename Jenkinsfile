pipeline {
  agent none
  stages {
        stage('Wave Hello') {
          agent { label 'default-node' }
          steps {
            echo 'Say something!'
            sh 'echo hello'
          }
        }

        stage('Nod Hello') {
          agent { label 'default-node' }
          steps {
            echo 'Go Team!'
          }
        }
        stage('Create File') {
          agent { label 'default-node' }
          steps {
            sh "echo hello-world > echo.txt"
          }
        }
        stage('Stash File') {
          agent { label 'default-node' }
          steps {
            stash 'echo.txt'
          }
        }
        stage('Unstash File') {
          agent { label 'default-node' }
          steps {
            unstash 'echo.txt'
          }
        }
        stage('Confirm Deploy to Staging') {
          agent none
          steps {
            input(message: 'Deploy to Stage', ok: 'Yes')
          }
        }
  }
}

