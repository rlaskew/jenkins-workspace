pipeline {
  agent none
  stages {
    stage('Wave Hello') {
      parallel {
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

      }
    }

  }
}
