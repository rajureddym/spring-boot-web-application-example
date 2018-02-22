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
                }
            }
            stage('Build') {
                steps {
 		   sh 'mvn install'
                }
           }	
       }
}
