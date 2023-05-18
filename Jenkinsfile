pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        sshagent(credentials:['ssh-iswebdev-green']) {
              sh 'rsync -rtz . green@iswebdev.ru:/var/www/html'
        }
        echo 'Success connect'
      }
    }
  }
}
