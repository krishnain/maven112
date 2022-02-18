@Library('sharedlibraries')_

pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/krishnain/maven112.git")
                }
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("172.31.14.150","testapp")
                }
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/intelliqittrainings/FunctionalTesting.git")
                    cicd.runSelenium("/home/ubuntu/.jenkins/workspace/Pipelinewithlibraries")
                }
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                script
                {
                    cicd.newApprovals("srinivas")
                    cicd.newDeploy("172.31.29.58","prodapp")
                }
            }
        }
        
        
        
        
    }
}
