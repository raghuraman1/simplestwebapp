pipeline {
  agent any
  stages {
    stage('Source') { // Get code
      steps {
        // get code from our Git repository
        git branch: 'main', url: 'https://github.com/raghuraman1/simplestwebapp.git'
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