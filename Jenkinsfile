pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        echo 'Hello World'
        sh 'ls -al'
        sh 'cat index.html'
      }
    }
    stage('Connect to server') {
      steps {
            sshagent(credentials:['ssh-iswebdev-green']) {
              sh 'ssh -o StrictHostKeyChecking=no green@iswebdev.ru'
            }
        echo 'Success connect'
      }
    }
  }
}
