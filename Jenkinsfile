pipeline {
  agent {
    node {
      label 'application'
    }
    
  }
  stages {
    stage('prep') {
      steps {
        sh '''gem install bundler
bundle install'''
      }
    }
  }
}