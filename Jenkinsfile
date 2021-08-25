pipeline {
	agent any
	tools {
  		jdk 'JDK11_Centos'
	}
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
					-s "./"
					-f "XML"
					--prettyPrint''', odcInstallation: 'Dependency-Check'
				dependencyCheckPublisher pattern: 'dependency-check-report.xml'
			}	
		}   
	}
}
