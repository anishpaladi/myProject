pipeline {
  agent any
  tools {
    maven 'maven01'
  }
  stages {
    stage('checkout') {
      steps {
        git 'git@github.com:sog1devopsint/myProject.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
  }
}
