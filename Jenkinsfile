pipeline {
	agent any
	stages{
		stage('Checkout') {
			steps{
				echo "------------>Checkout<------------"
					checkout scm
			}
		}
		stage('Dependency Analysis') {
			steps{
				steps {
						dependencyCheck additionalArguments: ''' 
							-o "./" 
							-s "./"
							-f "ALL" 
							--prettyPrint''', odcInstallation: 'Dependency-Check'
						dependencyCheckPublisher pattern: 'dependency-check-report.xml'
				}
			}
		}   
	}
}
