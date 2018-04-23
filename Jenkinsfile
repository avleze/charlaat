pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        tool(name: 'mvn', type: 'maven')
        sh 'mvn clean package'
      }
    }
  }
}