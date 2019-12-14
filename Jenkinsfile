pipeline {
	agent any
    tools {
    	maven 'maven3'
                 jdk 'JDK8'
    }
    stages {      
        stage('Build maven ') {
            steps { 
         
                    sh 'mvn  clean package'
          }
        } 
    }
}
