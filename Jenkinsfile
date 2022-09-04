// Declarative
pipeline {
	// agent { docker { image 'maven:3.8.6' }}
	agent { docker { image 'node' } }
	stages{
		stage('Build') {
			steps {
				sh 'node --version'
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
	}
	post {
		always {
			echo "Awesome. I run always!"
		}
		success {
			echo "If you see me then it is success!"
		}
		failure {
			echo "If you see this then it is fail!"
		}
		changed {
			echo "Change is constant"
		}
	}
}
