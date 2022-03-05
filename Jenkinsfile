pipeline 
{
    agent any

    environment {     
    	DOCKERHUB_CREDENTIALS = credentials('DOCKERHUB_CREDS')     
    }

    stages 
    {
        stage('Docker Build') 
        {   
            steps 
            {
                sh 'pwd'
                sh 'ls -al'
		sh 'docker version'
                sh 'echo "Creating Docker Image..."'
		sh 'docker build -t vasistaops/mypython:1.0 .'
		sh 'echo $DOCKERHUB_CREDENTIALS'
		sh 'echo $DOCKERHUB_CREDENTIALS_USR'
		sh 'docker push vasistaops/mypython:1.0'
            }
        }
    }
}
