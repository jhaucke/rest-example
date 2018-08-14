pipeline {
  agent any
  environment { 
    PADAM = 'Test123'
  }
  stages {
    stage('Build') {
      steps {
        echo '${PADAM}'
      }
    }
  }
}
