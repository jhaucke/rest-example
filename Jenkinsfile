pipeline {
  agent any
  environment { 
    PADAM = "Hallo/Test"
  }
  stages {
    stage('Build') {
      steps {
        sh "echo ${env.BRANCH_NAME} | tr / -"
      }
    }
  }
}
