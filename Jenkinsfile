pipeline {
  agent any
  environment {
    JENKINS_IS_FUN = 'Jenkins is fun'
  }
  stages {
        stage('Prod Only') {
          steps {
            echo 'Say something!'
            sh 'echo Prod_When!!'
          }
        }
        // stage('intermediate-pipeline Only'){
        //   when {
        //     beforeAgent true
        //     anyOf {
        //       branch 'intermediate-pipeline'
        //     }
        //   }
        //   steps {
        //     echo 'Say something!'
        //     sh 'echo Intermediate_Pipeline_When!!'
        //   }
        // }
        stage('Wave Hello') {
          agent { label 'default-node' }
          when {
            beforeAgent true
            anyOf
          }
          steps {
            echo 'Say something!'
            sh 'echo hello'
            echo "${env.GIT_COMMIT}"
            echo "${env.JENKINS_IS_FUN}"
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

