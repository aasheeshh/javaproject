pipeline
{
  agent any
  
  stages
  {
    stage('Compile')
    {
      steps
       {
         mvn compile
       }
    }
    
    stage('Test')
    {
      steps
      {
        mvn test
      }
    }
    
    stage('Package')
    {
      steps
      {
        mvn package
      }
    }
    
  }
}
