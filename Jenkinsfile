pipeline {
	agent any
    tools {
    	maven 'maven3'
                 jdk 'JDK8'
    }
    stages {      
        stage('Build maven ') {
            steps { 
                    sh 'pwd'
		    sh ' cd petclinic'
                    sh 'mvn  clean install package'
          }
        } 
    }
}
