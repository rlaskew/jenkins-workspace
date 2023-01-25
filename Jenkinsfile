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
            sh -c "echo 'Hello bacon!' > artifact.txt"
            // archiveArtifacts(artifacts: 'artifact*.txt', fingerprint: true)
      }
    }
  }
}