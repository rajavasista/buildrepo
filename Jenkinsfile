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
		sh 'docker build -t vasistaops/mypython:$BUILD_NUMBER .'
		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
		sh 'docker push vasistaops/mypython:$BUILD_NUMBER'
		sh 'echo "Push Completed!!!"'
            }
        }
    }
}
