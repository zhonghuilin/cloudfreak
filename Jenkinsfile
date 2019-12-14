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
		    sh 'cd /var/lib/jenkins/workspace/petclinic-build/petclinic'
		    sh 'pwd'
                    sh 'mvn  clean install package'
          }
        } 
    }
}
