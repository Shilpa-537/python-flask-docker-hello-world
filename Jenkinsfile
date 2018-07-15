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
                docker.withRegistry("https://your.ecr.domain.amazonws.com", "ecr:us-east-1:credential-id") {
 	              docker.image("your-image-name").push()
                }
            }
        }
    }
}



