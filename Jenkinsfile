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
                 stage('ContinuousDeployment')
                 {
                   steps
                   {
                    sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline4/webapp/target/webapp.war ubuntu@172.31.10.125:/var/lib/tomcat9/webapps/testapp.war'
                   }
                 }
                     
                   stage('ContinuousTesting')
                     {
                       steps
                       {
                        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                        sh 'java -jar /home/ubuntu/.jenkins/workspace/Declarativepipeline5/testing.jar'
                       }
                     }
                      
                     stage('ContinuousDelivery')
                 {
                   steps
                   {
                    sh 'scp /home/ubuntu/.jenkins/workspace/Declarativepipeline5/webapp/target/webapp.war ubuntu@172.31.15.129:/var/lib/tomcat9/webapps/prodapp.war'
                   }
                 }     
                    
          
          
          
          
          
            
    }
}
