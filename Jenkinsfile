node{
	stage('SCM Checkout'){
		git branch: 'wartomcat', url: 'https://github.com/sujandai/devopsprojects.git'
	}
	stage('Compile-Package'){
		def mvnHome = tool name: 'maven-3.5.4', type: 'maven'
		sh "${mvnHome}/bin/mvn package"
	}
}
