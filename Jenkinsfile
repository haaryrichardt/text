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
                    sh "scp -o StrictHostKeyChecking=no Service.yaml Deployment.yaml root@104.248.54.135:/home/user/"
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
                    sh "sshpass -p 'thegreat' ssh root@104.248.54.135 kubectl create -f /root/text/Deployment.yaml"
                }
            }
        }
     }
}
