pipeline {
  agent any
  environment { 
    PADAM = "${env.BRANCH_NAME}"
  }
  stages {
    stage('Build') {
      steps {
        sh "echo ${env.PADAM}"
      }
    }
  }
}
