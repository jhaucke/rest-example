pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'chmod +x mvnw'
        sh './mvnw clean package'
      }
    }
    stage('Test') {
      steps {
        sh './mvnw clean test'
      }
    }
    stage('Make Container') {
      steps {
        sh './mvnw install dockerfile:build'
      }
    }
  }
}