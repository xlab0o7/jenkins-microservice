pipeline {
	agent any
	//agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:PATH"
	}
	stages {
		stage('Build') {
			steps{
			   sh 'mvn --version'
			   sh 'docker version'
			   echo "Build"
			}
		}

		stage('Test') {
			steps{
				echo "Test"
			}
		}

		stage('integration Test') {
			steps{
			   echo "integration Test"
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