node {
stage('SCM Checkout')
{
git 'https://github.com/chandana-git/repo2.git'
}
stage('Compile Package from maven')
{
//since maven is installed as a plugin use tool in samsple step to find the command
def mvnHome = tool name: 'Maven 3.6.3', type: 'maven'
bat "${mvnHome}/bin/mvn clean package"
}
stage('Deploy to tomcat')
{
    deploy adapters: [tomcat9(credentialsId: 'e11d77ae-d6eb-41b6-9301-ce4b47c55079', path: '', url: 'http://localhost:9090/')], contextPath: null, war: 'target/JenkinsWar.war'
}
}
