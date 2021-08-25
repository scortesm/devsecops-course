pipeline {
	agent any
	stages{
		stage('Checkout') {
			steps{
				echo "------------>Checkout<------------"
					checkout scm
			}
		}
		// -f:Format, -o:out, -s:scan
		stage('Dependency Analysis') {
			steps {
				dependencyCheck additionalArguments: ''' 
					-o "./" 
					-s "./backup"
					-f "XML"
					--prettyPrint''', odcInstallation: 'Dependency-Check'
				dependencyCheckPublisher pattern: 'dependency-check-report.xml'
			}	
		}   
	}
}
