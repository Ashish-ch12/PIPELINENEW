pipeline {
	agent any
	
	parameters {
		choice(name: 'ENVIRONMENT', choices: ['QA','UAT'], description: 'Pick Environment value')
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/ashish/Documents/mavenfile/apache-maven-3.9.6/bin/mvn install'

	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENVIRONMENT == 'QA' ){
        	sh 'cp target/PIPELINE.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
        	echo "deployment has been done on QA!"
			 }
			else ( env.ENVIRONMENT == 'UAT' ){
    		sh 'cp target/PIPELINE.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			
			}}}	
}}
