pipeline {
  agent any
  stages {
    stage('SCM-Checkout') {
      parallel {
        stage('SCM-Checkout') {
          steps {
            ws(dir: '/var/lib/jenkins/CICD') {
              sh '''mkdir /var/lib/jenkins/workspace/CICD
cd /var/lib/jenkins/workspace/CICD'''
            }
            
            git(url: 'https://github.com/ravirajakoineni/CICD.git', branch: 'master', credentialsId: 'ravirajakoineni', poll: true)
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