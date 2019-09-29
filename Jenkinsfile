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
			stage('Deploy to Tomcat'){

				steps{
					sshagent(['172.31.44.18']) {
						sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.44.18:/var/lib/tomcat/webapps'
						}
					}
				}
			
			
			
			
		}
}
