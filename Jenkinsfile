pipeline {
  agent any
  environment { 
    PADAM = sh(returnStdout: true, script: "echo ${env.BRANCH_NAME} | tr / -")
  }
  stages {
    stage('Build') {
      steps {
        echo env.PADAM
      }
    }
  }
}
