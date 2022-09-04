// Declarative
pipeline {
	// agent { docker { image 'maven:3.8.6' }}
	// agent { docker { image 'node' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome =  tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	agent any
	stages{
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}
		stage('Integration Test') {
			steps {
				sh 'mvn failsafe:integration-test failsafe:verify'
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
