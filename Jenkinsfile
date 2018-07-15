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
                docker.withRegistry('https://016412741688.dkr.ecr.us-west-2.amazonaws.com', 'ecr:us-west-2:testing')
                docker.image('myapp2').push('latest')
            }
        }
    }
}



