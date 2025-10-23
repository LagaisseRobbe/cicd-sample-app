properties([pipelineTriggers([pollSCM('* * * * *')])])

pipeline {
    agent any
    stages {
    stage('Preparation') {
        steps {
            catchError(buildResult: 'SUCCESS') {
                sh 'docker stop samplerunning'
                sh 'docker rm samplerunning'
            }
        }
    }
 
    stage('Build') {
        build 'BuildSampleApp'
    }
    
    stage('Results') {
        build 'TestSampleApp'
    }
    }
    
}