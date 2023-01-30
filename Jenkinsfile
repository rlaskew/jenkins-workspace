@Library('shared-training-library') _
pipeline {
  agent any
  environment {
    JENKINS_IS_FUN = 'Jenkins is fun'
  }
  parameters {
    string(name: 'SAMPLE_INPUT', defaultValue: 'Bacon!', description: 'Sample Input for Testing')
  }
  stages {        
        stage('Intermediate-pipeline Branch Only') {
          agent { label 'default-node' }
          when {
            branch 'intermediate-pipeline'
          }
          steps {
            echo 'Say something!'
            sh 'echo hello'
            echo "${env.GIT_COMMIT}"
            echo "${env.GIT_BRANCH}"
            echo "${env.JENKINS_IS_FUN}"
          }
        }
        stage('Validate Shared Library'){
          agent { label 'default-node' }
          steps {
            singleton-library.info 'Starting'
            script {
              def z = new org.foo.Zot()
              z.echoHelloWorldWithName(name: 'Kevin Bacon')
            }
          }
        }
        stage('Main Branch Only') {
          agent { label 'default-node' }
          when {
            branch 'main'
          }
          steps {
            echo 'Say something!'
            sh 'echo hello'
            sh 'echo hello > hello.txt'
            sh 'cat hello.txt'
            sh 'ls -l'
            sh 'echo "is this picked up by default?"'
            echo "${env.GIT_COMMIT}"
            echo "${env.GIT_BRANCH}"
            echo "${env.JENKINS_IS_FUN}"
            archiveArtifacts(artifacts: '*.txt', fingerprint: true)
          }
        }
        stage('Wave Hello') {
          agent { label 'default-node' }
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
               echo "POST-always is awesome "
             } 
             success {
               echo "POST-success is awesome"
             } 
             failure {
               echo "POST-failure is NOT awesome"
             } 
          }
}

