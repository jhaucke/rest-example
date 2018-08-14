pipeline {
  agent any
  environment { 
    PADAM = "Hallo/Test"
  }
  stages {
    stage('Build') {
      steps {
        sh "PADAM = echo ${env.BRANCH_NAME} | tr / -"
        echo env.PADAM
      }
    }
  }
}
