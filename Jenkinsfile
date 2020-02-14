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
}
}

