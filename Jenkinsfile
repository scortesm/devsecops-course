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
	        echo '------------>Análisis de dependencias<------------'
	        dependencyCheckAnalyzer datadir: 'dependency-check-data', hintsFile: '', includeCsvReports: false, includeHtmlReports: true, includeJsonReports: false, includeVulnReports: true, isAutoupdateDisabled: false, outdir: '.', scanpath: '', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''
	        echo '------------>Análisis Finalizado<------------' 
	        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
	        echo '------------>Publicando Resultados<------------'

	    }
    }   
  }
}
