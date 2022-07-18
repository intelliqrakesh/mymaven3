pipeline
{
    agent any
    stages
    {
      stage('ContinuousDownload') 
      {
         steps
        {
         git 'https://github.com/intelliqrakesh/mymaven3.git' 
        }
      }
            stage('ContinuousBuild')
            {
              steps
              {
               sh 'mvn package'
              }
            }
        }
  }
