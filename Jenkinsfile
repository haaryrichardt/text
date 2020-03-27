pipeline
{
    agent any
    tools { maven "maven" }
    stages
    {
        stage ('Image Scanning')
        {
            steps
            {
                /*sh ‘echo “docker.io/haaryrix/accountsservices:latest” > anchore_images’
                anchore bailOnFail: false, bailOnPluginFail: false, name: 'anchore_images'*/
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
      }
        stage ('Deployment')
        {
            steps
            {
                sshagent(['Master']) 
                {
                sh 'cd /root/text'
                }
            }
        }
     }
}
