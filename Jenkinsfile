pipeline{
  agent any 
  tools {
    maven "maven3.9.1"
  }  
  stages {
    stage('1GetCode'){
      steps{
        sh "echo 'cloning the latest application version' "
        git branch: 'main', credentialsId: 'gitHubCredentials', url: 'https://github.com/ToneCode/maven-web-application'
      }
    }
    stage('3Test+Build'){
      steps{
        sh "echo 'running JUnit-test-cases' "
        sh "echo 'testing must passed to create artifacts ' "
        sh "mvn clean package"
      }
    }
    /*
    stage('4CodeQuality'){
      steps{
        sh "echo 'Perfoming CodeQualityAnalysis' "
        sh "mvn sonar:sonar"
      }
    }
    stage('5uploadNexus'){
      steps{
        sh "mvn deploy"
      }
    } 
    stage('8deploy2prod'){
      steps{
        deploy adapters: [tomcat(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.11.139:8080/')], contextPath: null, war: 'target/*war'
      }
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
