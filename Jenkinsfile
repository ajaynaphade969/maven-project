pipeline {
	
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
		}
	
}
