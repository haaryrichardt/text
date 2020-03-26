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
                sh "mvn clean package"
            }
      }
     }
}
