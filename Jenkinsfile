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

      }
    }

  }
}