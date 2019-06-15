pipeline {
    agent any

    tools {
	maven 'Maven 3.6.1'
    } 
    stages {
        stage('Build') { 
            steps {
                sh 'mvn clean compile' 
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'mvn -skipTests package'
		archiveArtifacts artifacts: '**/targets/*.jar', fingerprint: true
            }
        }
    }
}
