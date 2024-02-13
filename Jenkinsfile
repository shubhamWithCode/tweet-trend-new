pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    environment{
    	PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }

    stages {
        stage("build"){
		steps{
		sh 'mvn clean deploy'
		echo 'webhook setup is completed'
		}
	}

	stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'sonar-scanner'
    }
	
    tools {
        jdk "jdk11" // the name you have given the JDK installation using the JDK manager (Global Tool Configuration)
    }

    steps{
    withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }
    }
}
