pipeline {
  agent any
    tools {
      maven 'Maven-3.8.4'
                 jdk 'Java-11'
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
                   sh 'pwd'
		   sh 'cp -r target/*.jar docker'
           }
        }

        stage('Build docker image') {
           steps {
               script {
                 def customImage = docker.build('zhonghuilin/petclinic', "./docker")
                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                 customImage.push("${env.BUILD_NUMBER}")
                 }
           }
        }
	  }
    }
}
