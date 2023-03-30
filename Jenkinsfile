node{
	def mavenHome = tool name: 'maven3.9.1'
 stage('1.CodeClone'){
    git credentialsId: 'gitHubCredentials', url: 'https://github.com/LandmakTechnology/maven-web-application'
   }
 stage('2MavenBuild'){
   sh "${mavenHome}/bin/mvn package"
 }
 stage('3codeQuality'){
 	 sh "${mavenHome}/bin/mvn sonar:sonar"
 }
  stage('4UploadArtifacts'){
 	 sh "${mavenHome}/bin/mvn deploy"
 }
} 
  stage('8deploy2prod'){
      steps{
        deploy adapters: [tomcat(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.11.139:8080/')], contextPath: null, war: 'target/*war'
      }
  }
  post{
    always{
      emailext body: '''Hey guys
Please check build status.

Thanks
Landmark 
+1 661 433 2466''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'anthonywilliams314c@gmail.com'
    }
    success{
      emailext body: '''Hey guys
Good job build and deployment is successful.

Thanks
Landmark 
+1 661 433 2466''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'anthonywilliams314c@gmail.com'
    } 
    failure{
      emailext body: '''Hey guys
Build failed. Please resolve issues.

Thanks
Landmark 
+1 661 433 2466''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'anthonywilliams314c@gmail.com'
    }
  } 
  */
}
}
