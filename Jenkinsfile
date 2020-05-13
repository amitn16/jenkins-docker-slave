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
        git(url: 'https://github.com/amitn16/jenkins-docker-slave', branch: 'master', credentialsId: 'amitn16')
      }
    }

    stage('deploy') {
      agent any
      steps {
        sh '''ssh -o StrictHostKeyChecking=no root@192.168.1.109 /bin/bash
'''
      }
    }

  }
}