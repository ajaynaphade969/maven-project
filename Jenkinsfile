pipeline {
	agent any
		stages{
				stage('SCM Checkout'){
					steps{
					git 'https://github.com/ajaynaphade969/maven-project'
					}
				}
		
	
				stage ('Code test'){
					steps
					{
						withMaven(maven: 'MAVEN_HOME'){
						sh 'mvn test'
						}
					}
				}
			stage ('Code package'){
					steps
					{
						withMaven(maven: 'MAVEN_HOME'){
						sh 'mvn package'
						}
					}
				}
			
			stage ('Code install'){
					steps
					{
						withMaven(maven: 'MAVEN_HOME'){
						sh 'mvn install'
						}
					}
				}
			
		}
	
}
