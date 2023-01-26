pipeline {
  agent none
  stages {
    stage('Wave Hello') {
      agent { label 'default-node' }
      parallel {
        stage('Wave Hello') {
          steps {
            echo 'Say something!'
            sh 'echo hello'
          }
        }

        stage('Nod Hello') {
          steps {
            echo 'Go Team!'
          }
        }

      }
    }

  }
}
