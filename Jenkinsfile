node{
	stage('SCM Checkout'){
		git branch: 'wartomcat', url: 'https://github.com/sujandai/devopsprojects.git'
	}
	stage('Compile-Package'){
		def mvnHome = tool name: 'maven-3.5.4', type: 'maven'
		sh "${mvnHome}/bin/mvn package"
	}
	stage('Deploy to Tomcat'){
		sshagent(['tomcat-server']) {
		sh 'scp -o StrictHostKeyChecking=no target/*.war cloud_user@52.53.231.96:/opt/tomcat9/webapps/'
	}
   }
}
