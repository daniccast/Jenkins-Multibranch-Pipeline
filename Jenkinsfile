pipeline {
	agent any
	stages{
		stage('First') {
			steps{
				script {
					env.EXECUTE="true"
				}
			}
		}


		stage('Second'){
			when {
					environment name: 'EXECUTE', value: 'true'
			}
			steps{
				script{
					echo "Updating second stage"
					
				}
			}
		}
		
		stage ('Third') {
			when {
					environment name: 'EXECUTE', value: 'false'
				}
			steps {
				sh	'echo "Step three"'	
			}
		}
	}
}
