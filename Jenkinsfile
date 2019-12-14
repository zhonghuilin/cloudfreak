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
                    sh 'mvn  clean install package'
            }
        }
        
        stage('Copy Artifact') {
           steps { 
                   sh 'cp -r petclinic-build/target/*.war docker'
           }
        }
         
        stage('Build docker image') {
           steps {
                           
                 docker.build('prawinkorvi/petclinic-build/docker')
                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                 customImage.push(versionnum+"."+"${env.BUILD_NUMBER}")
                 }                     
           }
        }
	}
}
