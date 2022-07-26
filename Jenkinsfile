pipeline {
  agent any
  stages {
    stage('Source') { // Get code
      steps {
        // get code from our Git repository
       // git branch: 'main', url: 'https://github.com/raghuraman1/simplestwebapp.git'
       //or
       checkout scm
      }
    }
    stage('Build') { // Compile and do unit testing
      tools {
        maven 'm3'
      }
      steps {
        // run maven
        bat 'mvn clean package'
      }
    }
    
    stage('Deploy') { // deploy

      steps {
       deploy adapters: [tomcat9(credentialsId: 'awstomcatmghr', path: '', url: 'http://18.237.35.38:8080/')], contextPath: 'simplestwebapp', war: '**/*.war'
      }
    }
  }
}