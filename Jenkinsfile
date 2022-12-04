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

                sh "mvn -Dmaven.test.failure.ignore=true test"
            }
        }
        stage('Build') {
            steps {

                sh "mvn -Dmaven.test.failure.ignore=true package"
                sh "docker build -t tomcat:latest ."

            }
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
