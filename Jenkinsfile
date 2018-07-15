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
                docker.withRegistry ('https://016412741688.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:demo-ecr-credentials')
                sh 'docker tag myapp2:latest 016412741688.dkr.ecr.us-west-2.amazonaws.com/myapp2:latest'
                sh 'docker push 016412741688.dkr.ecr.us-west-2.amazonaws.com/myapp2:latest'
            }
        }
    }
}



