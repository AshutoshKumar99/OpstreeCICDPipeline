node 
{
stage('Project Name')
{
echo 'This is Opstree CI CD'
}

stage('Checkout Code')
{
git 'https://github.com/AshutoshKumar99/FastMaven.git'
}

stage('Build Code')
{

bat 'mvn clean install -Dmaven.test.failure.ignore=true'
}

stage ('JUnit report')
  {
    archive "target/**/*"
    junit 'target/surefire-reports/*.xml' 
  }


    stage('Deploy war to tomcat on ec2 machine')
        {
        sshagent(['Tomcat-Dev']) {
        sh 'scp -o StrictHostKeyChecking=no  sample.war ec2-user@52.66.56.87:/usr/share/tomcat7/webapps/'
        }}
  
  
 
  

}
