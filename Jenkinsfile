pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git url: 'https://github.com/your-username/my-python-app.git', branch: 'main'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          sh 'docker build -t python-app .'
        }
      }
    }

    stage('Run Tests in Docker') {
      steps {
        script {
          sh 'docker run --rm python-app'
        }
      }
    }
  }

  post {
    success {
      echo 'Build and tests passed!'
    }
    failure {
      echo 'Something went wrong!'
    }
  }
}