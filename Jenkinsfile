pipeline {
  agent any
  stages {
    stage('Source') { // Get code
      steps {
        // get code from our Git repository
        checkout scm
      }
    }
    stage('Build') { // Compile and do unit testing
      tools {
        maven 'm3'
      }
      steps {
        // run maven
        sh 'mvn clean package'
      }
    }
  }
}