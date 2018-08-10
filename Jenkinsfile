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
        branch 'master'
      }
      steps {
        sh './mvnw install dockerfile:build'
      }
    }
  }
}
