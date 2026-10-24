pipeline{
  agents any
  tools{
    maven 'mymaven'
  }
  stages{
    stage ('clone the repo')
    {
      steps {
        git 'https://github.com/Lpurushotham/DevOpsCodeDemo.git'
      }
    }
    stage{
      stage ('build the code')
      {
        steps{
         sh 'mvn package'
        }
      }
    }
    stage ('deploy the code')
    {
      steps{
       deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tom-credentials', path: '', url: 'http://18.219.13.37:8080/')], contextPath: null, war: '**/*.war'
      }
    }
  }
}
