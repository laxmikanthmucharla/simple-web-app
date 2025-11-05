pipeline {
agent 	{
			label 'JavaBuildServer'
		}
tools	{
			maven 'localMaven'
		}
stages	{
		stage ( 'Build' )	{
								steps 	{
											sh 'mvn clean package'
										}
								post	{
											success {
													echo 'maven clean package executed'
													archiveArtifacts artifacts: '**/target/*.war'
													}
										}
								
							}
		stage ( 'Deployments' )	{
									steps	{
												echo 'deploying application'
												sh 'pwd'
												deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat-credentials', path: '', url: 'http://13.211.239.170:8080')], contextPath: null, war: '*.war'
											}
											
								}
		}
}
