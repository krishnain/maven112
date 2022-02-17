pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Loans')
        {
            steps
            {
                git 'https://github.com/krishnain/maven112.git'
            }
        }
        stage('ContinuousBuild_Loans')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        
        
        
    }
}
