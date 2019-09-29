pipeline {
	agent any{
		stages{
				stage('SCM Checkout'){
					git 'https://github.com/ajaynaphade969/maven-project'
			
				}
	
	
				stage ('Code test'){
					withMaven(maven: 'MAVEN_HOME'){
						sh 'mvn test'
					}
				}
				stage('compile'){
					withMaven(maven: 'MAVEN_HOME'){
						sh 'mvn compile'
					}
				}
		}
	}
}
