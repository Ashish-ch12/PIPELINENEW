pipeline {
	agent any
	
	parameters {
		choice(name: 'ENV', choices: ['QA','UAT'], description: 'Pick Environment value')
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
			 if ( env.ENV == 'QA' ){
        	sh 'cp target/PIPELINENEW.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
        	echo "deployment has been done on QA!"
			 }
			else if ( env.ENV == 'UAT' ){
    		sh 'cp target/PIPELINENEW.war /home/ashish/Documents/mavenfile/apache-tomcat-9.0.88/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			slackSend baseUrl: 'https://hooks.slack.com/services', channel: 'devops-slack', color: 'good', message: 'welcome to jenkins', teamDomain: 'ashish'
			}}}	
}}
