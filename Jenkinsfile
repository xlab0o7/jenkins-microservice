pipeline {
	agent any
	//agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Complile') {
			steps{
			   //sh 'mvn --version'
			   //sh 'docker version'
			   sh "mvn clean compile"
			}
		}

		stage('Test') {
			steps{
				sh "mvn test"
			}
		}

		stage('integration Test') {
			steps{
			   sh " mvn failsafe:integration-test failsafe:verify"
			}
		}
	}	

	post {
		always { 
			echo 'i will run always'
		}
		success {
			echo 'i will run when this build will successfully completed'
		}
		failure {
			echo 'i will run when there is any failure'
		}
	}
}