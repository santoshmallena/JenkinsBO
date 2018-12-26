pipeline {
  agent {
    docker {
      image 'maven:30309-jdk-8'
    }

  }
  stages {
    stage('initialize') {
      steps {
        sh 'mvn clean'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }
    stage('Reports') {
      steps {
        junit '**/build/test-reports/*.xml'
      }
    }
  }
}