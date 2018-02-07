pipeline {
  agent any
  stages {
    stage('SCM-Checkout') {
      parallel {
        stage('SCM-Checkout') {
          steps {
            git(url: 'https://github.com/ravirajakoineni/CICD.git', branch: 'master', credentialsId: 'ravirajakoineni', poll: true)
          }
        }
        stage('') {
          steps {
            validateDeclarativePipeline '/var/lib/jenkins/workspace/CICD/Jenkisfile'
          }
        }
      }
    }
  }
}