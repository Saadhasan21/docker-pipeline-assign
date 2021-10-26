pipeline{
    agent any

    stages{
        stage('test'){
            echo 'deploy'   
        }
        stage('Build'){
            sh 'docker build -t saad3001/app:1.0.0 .'
        }
        stage('Push'){
            withCredentials([string(credentialsId: 'docker-pwd1', variable: 'dockerHubPwd')]) {
                sh "docker login -u saad3001 -p ${dockerHubPwd}"
            }
            sh 'docker push saad3001/app:1.0.0 .'
        }
        stage('Deploy'){
            echo 'deploy'
        }
    }
}