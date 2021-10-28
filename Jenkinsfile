pipeline {
  agent any
  triggers {
      pollSCM "* * * * *"
  }
  tools {
    
     maven 'M2_HOME'
  }
  environment {
    registry = "cabral2604/repository_name"
    registryCredential = 'dockerhub'
  }
  stages {
    stage('Build') {
      steps {
        sh "mvn clean"
        sh "mvn install"
        sh "mvn package"
        sh "mvn test"
      }
    }
    stage('test') {
      steps {
        echo "test step"
        sh "mvn test"
        sleep 10
      }
    }
    stage('compile') {
      steps {
        echo "compile"
        sleep 10
      }
    }
    stage('deploy') {
      steps {
        script {
          docker.build registry + ":$BUILD_NUMBER"
        
      }
    }
  }
}
