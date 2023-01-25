pipeline {
  agent any
  environment {
    BUZZ_NAME = "WORKER BEE"
  }
  stages {
    parallel {
      stage('Buzz Build') {
        steps {
              echo 'Hello World!'
              sh 'java -version'
        }
      }
      stage('Buzz Test') {
        steps {
              echo 'Hello World!'
              sh 'java -version'
              echo 'I am ${BUZZ_NAME}'
        }
      }
    stage('Generate Artifact') {
      steps {
            echo 'Hello World!'
            sh "ls -l"
            script {
                 def data = "Hello Artifact"
                 writeFile(file: 'artifact.txt', text: data)
                 sh "ls -l"
            }
            archiveArtifacts(artifacts: 'artifact*.txt', fingerprint: true)
      }
    }
    }
  }
}