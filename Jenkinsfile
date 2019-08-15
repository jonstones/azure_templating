pipeline {
  agent any
  stages {
    stage('Approval') {
        input "Approve this change?"
      }
    stage('Build') {
      steps {
        echo 'I am building'
      }
    }
  }
}