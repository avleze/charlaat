pipeline {    
    agent any
    
    tools {
        maven 'mvn'
        jdk 'jdk8'
    }
    
    options {
    	buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    
    environment {
    	groupId = readMavenPom().getGroupId()
	artifactId = readMavenPom().getArtifactId()
	version = readMavenPom().getVersion()
    }
    
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
        }

        stage ('Delivery') {
            steps {
		sh '''
                        echo "Dejando JAR"
                '''
            }
        }

        stage ('Deploy') {
            steps {
                sh '''
                	echo "Desplegando en el Server"
                '''
            }
        }
        
    }

}


