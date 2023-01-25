pipeline {
  agent any
  stages {
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
      }
    }
    stage('Generate Artifact') {
      steps {
            echo 'Hello World!'
            // echo 'Hello Artifact!' > artifact.txt
            // archiveArtifacts(artifacts: 'artifact*.txt', fingerprint: true)
      }
    }
  }
}