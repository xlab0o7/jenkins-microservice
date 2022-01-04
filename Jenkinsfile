pipeline {
	agent any
	stages {
		stage('Build') {
			steps{
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