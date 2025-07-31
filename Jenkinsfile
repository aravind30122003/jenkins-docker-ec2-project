pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/aravind30122003/Jenkins-docker-ec2-project.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build('myflaskapp')
        }
      }
    }

    stage('Run Docker Container') {
      steps {
        script {
          sh 'docker stop myflaskapp || true'
          sh 'docker rm myflaskapp || true'
          sh 'docker run -d -p 80:5000 --name myflaskapp myflaskapp'
        }
      }
    }
  }
}
