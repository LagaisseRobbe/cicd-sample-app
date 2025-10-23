properties([pipelineTriggers([pollSCM('* * * * *')])])

pipeline {
  agent any

  stages {
    stage('Preparation') {
      steps {
        sh 'docker rm -f samplerunning || true'
      }
    }

    stage('Build') {
      steps {
        build job: 'BuildSampleApp'
      }
    }

    stage('Results') {
      steps {
        build job: 'TestSampleApp'
      }
    }
  }
}
