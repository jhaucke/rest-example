pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'chmod +x mvnw'
        sh './mvnw clean package'
        archiveArtifacts(artifacts: 'target/*.jar', onlyIfSuccessful: true)
      }
    }
    stage('Test') {
      parallel {
        stage('Test 1') {
          steps {
            sh './mvnw clean test'
            junit '**/surefire-reports/**/*.xml'
          }
        }
        stage('Test 2') {
          steps {
            sh 'ping -c 5 localhost'
          }
        }
      }
    }
    stage('Make Container') {
      when {
        anyOf {
          branch 'master'
          branch 'release/*'
        }
      }
      steps {
        sh './mvnw install dockerfile:build'
      }
    }
    stage('Deploy') {
      steps {
        script {
          if (env.BRANCH_NAME == 'master') {
            echo 'Deploying master branch...'
          }
          if (env.BRANCH_NAME.contains('release')) {
            echo 'Deploying release branch'
          }
          if (env.BRANCH_NAME.contains('feature')) {
            echo 'Deploying feature branch'
          }
        }
      }
    }
  }
}
