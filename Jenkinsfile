pipeline {
  agent any
  tools {
     maven 'M2_Home'
  }
  stages {
    stage('Build') {
      steps {
        sh "mvn clean"
        sh "mvn install"
        sh "mvn package
      }
    }
    stage('test') {
      steps {
        echo "test step"
        sh "mvn test"
        sleep 10
      }
    }
    stage('deploy') {
      steps {
        echo "deploy step"
        sleep 10
      }
    }
    stage('docker') {
      steps {
        echo "image step"
        sleep 10
      }
    }
  }
}
