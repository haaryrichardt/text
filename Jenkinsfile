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
                sh ‘echo “docker.io/haaryrix/accountsservices:latest” > anchore_images’
                anchore bailOnFail: false, bailOnPluginFail: false, name: 'anchore_images'
            }
      }
     }
}
