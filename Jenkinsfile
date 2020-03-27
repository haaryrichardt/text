pipeline
{
    agent any
    tools { maven "maven" }
    stages
    {
        /*stage ('Image Scanning')
        {
            steps
            {
                script
                {
                    node
                    {
                    def imageLine = 'haaryrix/accountsservices:latest'
                    writeFile file: 'anchore_images', text: imageLine
                    anchore bailOnFail: false, bailOnPluginFail: false, name: 'anchore_images'
                    }
                }
            }
        }*/
        stage ('Deployment')
        {
            steps
            {
                sshagent(['Master']) 
                {
                sh "scp -o StrictHostKeyChecking=no Service.yaml Deployment.yaml root@104.248.54.135:/home/user/"
                }
            }
        }
     }
}
