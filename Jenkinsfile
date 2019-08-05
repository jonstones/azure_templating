pipeline {
  agent {
    docker {
      image 'dishcloth / az_terraform_worker'
      args 'test'
    }

  }
  stages {
    stage('test') {
      steps {
        sh 'echo "hello world"'
      }
    }
    stage('') {
      steps {
        sh 'echo "hello world"'
      }
    }
  }
}