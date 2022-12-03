pipeline
{
  agent any
  
  stages
  {
    stage('Compile')
    {
      steps
       {
         echo 'compile'
         # mvn compile
       }
    }
    
    stage('Test')
    {
      steps
      {
        echo 'test'
        # mvn test
      }
    }
    
    stage('Package')
    {
      steps
      {
        echo 'package'
        # mvn package
      }
    }
    
  }
}
