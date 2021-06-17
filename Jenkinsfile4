

pipeline{
	agent any
	
	stages {
		
		stage ("scm-fetch") {
			steps{
				echo 'Fetching Source Code management from GITHUB'
			}
		}
		
		stage ("build") {
			steps{
				echo 'Code compilation and packaging'
			}
		}
	
		stage ("Test") {
			steps{
				echo 'Executing Test cases'
			
			}
		}
	}
}