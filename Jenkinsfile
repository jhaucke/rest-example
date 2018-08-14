pipeline {
  agent any
  environment { 
    PADAM = "${env.BRANCH_NAME} | tr / -"
  }
  stages {
    stage('Build') {
      steps {
        echo env.PADAM
      }
    }
  }
}
