pipeline {
  agent any
  stages {
    stage('start') {
      steps {
        echo 'Start -1'
      }
    }

    stage('pull') {
      steps {
        git(url: 'https://github.com/bibinwilson/jenkins-docker-slave', branch: 'master', credentialsId: 'amitn16')
      }
    }

    stage('deploy') {
      steps {
        node(label: 'java-docker-slave') {
          echo 'docker'
        }

      }
    }

  }
}