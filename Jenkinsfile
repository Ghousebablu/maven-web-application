node
{
    
def mavenHome = tool name: "maven3.8.5"
  properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
 
 echo "The Job name is: ${env.JOB_NAME}"
 echo "The Node name is:${env.NODE_NAME}"
 echo "The workspace path is: ${env.WORKSPACE}"
 echo "The node label is: ${env.NODE_LABELS}"
 echo "The build number is: ${env.BUILD_NUMBER}"
 
stage('CheckoutCode'){
git branch: 'development', credentialsId: '0597cb78-4198-4be8-af15-6f7530e9c51b', url: 'https://github.com/Ghousebablu/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

  /*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatServer'){
sshagent(['2a3608a1-2e0e-4da2-8843-78805fd6075f']) {
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@43.205.119.185:/opt/apache-tomcat-9.0.65/webapps/"
}
}

*/
  
}
