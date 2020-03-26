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
                writeFile file: anchorefile, text: 'haaryrix/accountsservices:latest'
                anchore bailOnFail: false, bailOnPluginFail: false, name: 'anchore_images'
            }
      }
     }
}
