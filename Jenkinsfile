pipeline {
agent 	{
			label 'JavaBuildServer'
		}
tools	{
			maven 'localMaven'
		}
stages	{
		stage ( "build" )	{
								steps 	{
											sh 'mvn clean package'
										}
								post	{
											success {
													echo 'maven clean package executed'
													}
										}
							}
		}
}
