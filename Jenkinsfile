pipeline {
	agent any
	tool{
	  maven	'Maven'
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn clean install'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.xml'
				}
			}
		}

	stage ('run') {
			steps {
			   sh './scripts/deliver.sh'
			}
	    }
   }
}

