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
      steps {
        sh './mvnw clean test'
        junit '**/surefire-reports/**/*.xml'
      }
    }
    stage('Make Container') {
      steps {
        sh './mvnw install dockerfile:build'
      }
    }
  }
}