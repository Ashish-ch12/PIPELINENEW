pipeline {
	agent any 
	
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
		sh 'cp target/PIPELINENEW.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
			}}	
}}
