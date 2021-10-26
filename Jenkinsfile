pipeline{
    agent any

    stages{
        stage('test'){
            sh 'node --version'   
        }
        stage('Build'){
            sh 'docker build -t saad3001/app:1.0.0 .'
        }
        stage('Push'){
            withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                sh "docker login -u saad3001 -p ${dockerHubPwd}"
            }
            sh 'docker push saad3001/app:1.0.0 .'
        }
        stage('Deploy'){
            echo 'deploy'
        }
    }
}