pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/avi3030/ciProject.git', branch: 'main')
      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -f curriculam-front/Dockerfile .'
      }
    }

    stage('Dockerhub login') {
      environment {
        DOCKERHUB_USER = 'avinashdevops03'
        DOCKERHUB_PASSWORD = 'Avikar@555'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}