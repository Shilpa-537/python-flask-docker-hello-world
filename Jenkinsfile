pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build -t myapp2 .'
            }
        }
        stage('Push image to ecr') {
            steps {
                sh 'sudo docker images'
                script {
                  docker.withRegistry('https://123456789122.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:demo-ecr-credentials') 
				  {
                   docker.image('hello-world').push('latest')
                  }
                }
            }
        }
    }
}



