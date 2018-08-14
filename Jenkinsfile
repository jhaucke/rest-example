pipeline {
  agent any
  environment { 
    PADAM = "echo ${env.BRANCH_NAME} | tr / -"
  }
  stages {
    stage('Build') {
      steps {
        echo env.PADAM
      }
    }
  }
}
