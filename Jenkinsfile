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
                sh 'mvn -DskipTests package'
		archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
