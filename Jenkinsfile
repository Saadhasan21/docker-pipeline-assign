pipeline
{
    agent any

    environment
    {
		DOCKERHUB_CREDENTIALS=credentials('docker-pwd')
	}

    stages
    {
        stage('Test')
        {
            steps
            {
                echo "testing"
            }
        }

        stage('Build')
        {
            steps
            {
                echo "Building"

                sh "docker build -t saad3001/app:1.0.0 ."
            }
        }

        stage('Login')
        {

			steps
            {
                echo "Login Succesfully!"

				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

        stage('Push')
        {
            steps
            {
                echo "Pushing the React App developed by hafizaatifkamal & Team"

                sh "docker push saad3001/app:1.0.0"
            }
        }

        stage('Diploy')
        {
            steps
            {
                echo "Deploying"

                sh "docker pull saad3001/app:1.0.0"

                sh "docker run saad3001/app:1.0.0 "
            }
        }
    }
}