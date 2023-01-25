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