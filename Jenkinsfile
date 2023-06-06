pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        git(url: 'https://github.com/GabeD23/flasking.git', branch: 'main')
      }
    }

    stage('Docker Build') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'docker build -t gabed23/flask_app .'
      }
    }

    stage('Docker Login') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'docker login -u gabed23 -p dckr_pat_JUzDkU4RQFBwFWxuD0CYHSNIwMc'
      }
    }

    stage('Docker Push') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'docker push gabed23/flask_app'
      }
    }

  }
}