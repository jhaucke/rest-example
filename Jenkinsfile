pipeline {
  agent any
  environment { 
    PADAM = env.BRANCH_NAME
  }
  stages {
    stage('Build') {
      steps {
        echo env.PADAM
      }
    }
  }
}
