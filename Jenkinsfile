node('master') 
{
    stage('continousdownload') 
    {
    git 'https://github.com/SIVAPRACTICE1/java-code.git'
    }
    stage('continousbuild') 
    {
    sh 'mvn package'
    }
    stage('continousdeploy') 
    {
    sh 'scp /var/lib/jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.62.88:/var/lib/tomcat9/webapps/qaapp.war'
    }
    stage('continoustest')
    {
    git 'https://github.com/SIVAPRACTICE1/testing-scripts.git'
    sh 'java -jar /var/lib/jenkins/workspace/development/testing.jar'
    }
    stage('continousdelivery')
    {
    sh 'scp /var/lib/jenkins/workspace/development/webapp/target/webapp.war ubuntu@172.31.29.126:/var/lib/tomcat9/webapps/prodapp.war'
    }
}    
