pipeline {
  agent any
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            echo 'Hello World!'
            sh 'java -version'
          }
        }

        stage('Say Goodbye') {
          steps {
            echo 'Goodbye!'
            sleep 1
          }
        }
        stage('Say Goodbye Again! from github editor') {
          steps {
            echo 'Goodbye!'
            sleep 1
          }
        }

      }
    }

    stage('Wave Hello') {
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
