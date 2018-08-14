pipeline {
  agent any
  environment { 
    PADAM = sh("echo ${env.BRANCH_NAME} | tr / -")
  }
  stages {
    stage('Build') {
      steps {
        echo env.PADAM
      }
    }
  }
}
