pipeline 
{
agent any
tools
{
maven "Maven"
}
stages {
 stage('Github')
{
  steps{
   git credentialsId: 'github', url: 'https://github.com/ravigithud/spring3-mvc-maven-xml-hello-world.git'
  }
}

stage('Maven installation')
{
steps
{
 sh label: '', script: 'mvn clean package'
 }
 }
  stage('Nexus installation')
    {
    steps
     {
       nexusPublisher nexusInstanceId: '9000', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: '/var/lib/jenkins/workspace/pipeline2/target/spring3-mvc-maven-xml-hello-world-1.2.war']], mavenCoordinate: [artifactId: 'servlet', groupId: 'Indus', packaging: 'war', version: '$BUILD_ID']]]
     }
    }
  stage('Tomcat')
  {
  steps
  {
  deploy adapters: [tomcat8(credentialsId: '123', path: '', url: 'http://13.233.233.109:8080')], contextPath: null, war: '**/*.war'
  }
}  
   }
 }
 
 
