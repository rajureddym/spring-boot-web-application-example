pipeline {
	agent any


	tools {
		jdk 'java8'
		maven 'maven3'
        }

	stages {
            stage('Init'){
	        steps {
	           sh '''
                      echo "PATH =${PATH}"
   		      echo "M2_HOME = ${M2_HOME}"
                   ''' 
               }
            stage('Build') {
                steps {
 		   sh 'mvn install'
                }
           }	
           stage('Testing') {
                steps {
           	   sh '''
                       sudo docker build -t spring-boot-docker:${BUILD_NUMBER} ${WORKSPACE} 
                       sudo docker run -p 8889:8080 spring- boot-docker:${BUILD_NUMBER} 
                   '''         
                }  
           }
 
          
       }
}
