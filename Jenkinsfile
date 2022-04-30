@Library('DevOps_Library@master') _
node
{

	stage('Source CheckOut')
    {
		SourceCheckout("https://github.com/Ayyappa376/Demo_Devops.git","master",)
	}
	stage('Maven Build')
	{
		BuildMaven("clean install")
	}
	stage('Upload Artifact')
	{
		UploadArtifacts("war","target/Demo.war","demo","com.mydemo","nexus_cred","Build-Snapshots","${BUILD_NUMBER}-SNAPSHOT")
	}
	stage('Dev Deployment')
	{
		ConfirmMessage()
		TomcatDeploy("target\\Demo.war",'"C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"')
	}	
}
