pipeline 
{
    agent any

    environment {     
    	DOCKERHUB_CREDENTIALS = credentials('DOCKER_CREDS')     
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
		sh 'docker login -u $DOCKERHUB_CREDENTIALS_USR -p DOCKERHUB_CREDENTIALS_PWD'
		sh 'docker push vasistaops/mypython:1.0'
            }
        }
    }
}
