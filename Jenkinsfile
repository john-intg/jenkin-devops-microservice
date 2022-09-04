// Declarative
pipeline {
	agent any
	stages{
		stage('Build') {
			steps {
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} post {
		always {
			echo "Awesome. I run always!"
		}
		success {
			echo "If you see me then it is success!"
		}
		failure {
			echo "If you see this then it is fail!"
		}
	}
}
