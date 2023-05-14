pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        echo 'Hello World'
      }
    }
    stage('Deploy') {
      steps {
        sshagent(credentials:['ssh-iswebdev-green']) {
              sh 'ssh -o StrictHostKeyChecking=no green@iswebdev.ru'
              sh 'rsync -rtz --progress . green@iswebdev.ru:/var/www/html'
        }
        echo 'Success connect'
      }
    }
  }
}
