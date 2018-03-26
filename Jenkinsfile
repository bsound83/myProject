pipeline {
  agent { label 'linux' }
  toolls { 
    maven 'M3'
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/bsound83/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
