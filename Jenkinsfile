pipeline 
{
    agent any

    tools 
    {

        maven "Maven_3"
    }

    stages 
    {
        stage('Build') 
        {
            steps 
            {
                sh "mvn clean compile"
            }

        }    
        stage('test') 
        {
            steps 
            {
                sh "mvn test"
            }
        
        }
        stage('deploy') 
        {
            steps 
            {
                sh "mvn deploy"
            }
            post
            {
                success
                {
                    emailext body: 'Deployed successfully ', recipientProviders: [developers()], subject: 'Pipeline status', to: 'shivi.verma332@gmail.com'
                }
            }
        
        }
    }
}
