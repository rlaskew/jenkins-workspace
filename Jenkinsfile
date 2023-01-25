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
            echo 'Hello Artifact!' > artifact.txt
            echo ${PWD}
            ls ${PWD}
            archiveArtifacts(artifacts: 'artifact*.txt', fingerprint: true)
      }
    }
    stage('List Artifact') {
      steps {
            echo ${JENKINS_HOME}
            ls ${JENKINS_HOME}
            ls ${JENKINS_HOME}/fingerprints
      }
    }
  }
}