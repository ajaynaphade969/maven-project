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
			
			sshPublisher(publishers: [sshPublisherDesc(configName: 'tomcat', 
								   transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
			
			
			
			
		}
	
}
