node {
  stage 'Docker build'
  sudo docker build -t myapp2 .
  stage 'Docker push'
  docker.withRegistry('https://016412741688.dkr.ecr.us-west-2.amazonaws.com', 'ecr:us-west-2:testing') {
    docker.image('myapp2').push('latest')
  }
}

