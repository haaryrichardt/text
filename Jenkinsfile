pipeline
{
    agent any
    tools { maven "maven" }
    stages
    {
     stage ('Build and Package')
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
                    anchore name: 'anchore_images'
                    bailOnFail: false
                    }
                }
            }
      }
     }
}
