pipeline {
	//agent any
	agent { docker { image 'node:13.8' } }
	stages {
		stage('Build') {
			steps{
			   sh 'node --version'
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