pipeline {
  agent default-node
  stages {
        stage('Wave Hello') {
          agent { label 'default-node' }
          steps {
            echo 'Say something!'
            sh 'echo hello'
          }
          post {
             always {
               echo "POST-always is awesome"
             } 
             success {
               echo "POST-success is awesome"
             } 
             failure {
               echo "POST-failure is NOT awesome"
             } 
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
  post {
             always {
               echo "POST-always is awesome"
             } 
             success {
               echo "POST-success is awesome"
             } 
             failure {
               echo "POST-failure is NOT awesome"
             } 
          }
}

