pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        tool(name: 'mvn', type: 'maven')
        tool(name: 'j8', type: 'java')
        sh 'mvn clean package'
      }
    }
  }
}