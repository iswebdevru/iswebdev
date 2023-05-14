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
        sh 'pwd'
        sh 'ls -al'
        sshagent(credentials:['ssh-iswebdev-green']) {
              sh 'ssh -o StrictHostKeyChecking=no green@iswebdev.ru'
              sh 'rsync -rtz --progress . green@iswebdev.ru:/var/www/html1'
        }
        echo 'Success connect'
      }
    }
  }
}
