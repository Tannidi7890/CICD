pipeline {
  agent any
  stages {
    stage('SCM-Checkout') {
      parallel {
        stage('SCM-Checkout') {
          steps {
            git(url: 'https://github.com/ravirajakoineni/CICD.git', branch: 'master', credentialsId: 'ravirajakoineni', poll: true, changelog: true)
            ws(dir: '/var/lib/jenkins/CICD') {
              sh 'CD /var/lib/jenkins/workspace/CICD'
            }
            
          }
        }
        stage('error') {
          steps {
            validateDeclarativePipeline '/var/lib/jenkins/workspace/CICD/Jenkisfile'
          }
        }
      }
    }
  }
}