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
      steps {
        node(label: 'java-docker-slave') {
          echo 'docker'
        }

        sh '''ssh -tt root@192.168.1.109 
docker run -d -it --name node3 -p 2222:22 bibinwilson/jenkins-slave'''
      }
    }

  }
}