pipeline {
  agent {
    docker {
      image 'dishcloth/az_terraform_worker:latest'
      args 'test'
    }

  }
  stages {
    stage('test') {
      steps {
        sh 'echo "hello world"'
      }
    }
    stage('test1') {
      steps {
        sh 'echo "hello world"'
      }
    }
  }
}