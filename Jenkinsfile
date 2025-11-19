pipeline
{
  agent any
  
  tools
  {
    maven 'Maven_Base'
  }
  
  triggers
  {
    pollSCM('* * * * *')
  }
  
  stages
  {
    stage('Checkout Code from GitHub')
    {
      steps()
      {
        git branch: 'development', credentialsId: '957b543e-6f77-4cef-9aec-82e9b0230975', url: 'https://github.com/devopstrainingblr/maven-web-application-1.git'
      }
    }
    
    stage('Build Project')
    {
      steps()
      {
        sh "mvn clean package"
      }
    }
    
    stage('Execute SonarQube Report')
    {
      steps()
      {
        sh "mvn clean sonar:sonar"
      }
    }
    
    stage('Upload Artifacts to Sonatype Nexus')
    {
      steps()
      {
        sh "mvn clean deploy"
      }
    }
    
    stage('Deploy Application to Tomcat')
    {
      steps()
      {
        sshagent(['bfe1b3c1-c29b-4a4d-b97a-c068b7748cd0'])
        {
          sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@35.154.190.162:/opt/apache-tomcat-9.0.50/webapps/"
        }
      }
    }
  }
}
