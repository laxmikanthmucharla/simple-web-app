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
								
							}
		stage ( 'Deployments' )	{
									steps	{
												echo 'deploying application'
												deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat-credentials', path: '', url: 'http://3.25.101.137:8080/')], contextPath: null, war: 'target/*.war'
											}
											post	{
											success {
													echo 'maven clean package executed'
													archiveArtifacts artifacts: '**/target/*.war'
													}
													}
								}
		}
}
