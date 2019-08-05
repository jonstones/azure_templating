pipeline {
  agent {
    docker {
      image 'apline'
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