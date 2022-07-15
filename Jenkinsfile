node('built-in')
{
  stage('ContinuousDownload')
    {
     git 'https://github.com/intelliqittrainings/maven.git'
    }
       stage('ContinuousBuild') 
       {
       sh 'mvn package'
       }
           stage('ContinuousDeploy') 
           {
            deploy adapters: [tomcat9(credentialsId: '1481eef3-175e-475c-b8cf-b5626ae362ff', path: '', url: 'http://172.31.10.125:8080')], contextPath: 'testapp', war: '**/*.war'
           }
              stage('ContinuousTesting') 
              {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline1/testing.jar'
              }
                 stage('ContinuousDelivery') 
                 {
                 deploy adapters: [tomcat9(credentialsId: 'b69caf85-2aae-4725-bf44-3bc571abd9e6', path: '', url: 'http://172.31.15.129:8080')], contextPath: 'prodapp', war: '**/*.war'
                 }
}
