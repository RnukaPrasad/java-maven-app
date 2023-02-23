pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'clean install'
			}
		}
		stage('Test') {
			steps {
				sh 'test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.xml'
				}
			}
		}
		
	}
}
