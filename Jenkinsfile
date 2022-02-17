pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Master')
        {
            steps
            {
                git 'https://github.com/krishnain/maven112.git'
            }
        }
        stage('ContinuousBuild_Master')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment_Master')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.14.150:/var/lib/tomcat9/webapps/testapp.war'
            }
        }
        stage('ContinuousTesting_Master')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline/testing.jar'
            }
        }
        stage('ContinuosuDelivery_Master')
        {
            steps
            {
              input message: 'Waiting for Approval from the DM!', submitter: 'srinivas'
              
sh 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.29.58:/var/lib/tomcat9/webapps/prodapp.war'
            }
        }
        
        
        
    }
}
