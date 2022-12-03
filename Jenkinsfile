pipeline 
{
    agent any

    stages 
    {
        stage('Compile') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/aasheeshh/javaproject.git'
                sh "mvn -Dmaven.test.failure.ignore=true clean compile"
            }
        }
        stage('Test') {
            steps {
                git branch: 'main', url: 'https://github.com/aasheeshh/javaproject.git'

                sh "mvn -Dmaven.test.failure.ignore=true clean test"
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/aasheeshh/javaproject.git'

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }

        stage('post')
        {
            post 
            {
                success 
                {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.war'
                }
            }
        }
    }
}
