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
                echo 'building'
            }

        }    
        stage('test') 
        {
            steps 
            {
                echo 'testing'
            }
        
        }
        stage('deploy') 
        {
            steps 
            {
                echo 'deployment'
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
