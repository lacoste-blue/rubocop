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
    stage('verify') {
      parallel {
        stage('verify') {
          steps {
            sh 'bundle exec rspec'
          }
        }
        stage('lint') {
          steps {
            sh 'bundle exec rubocop'
          }
        }
        stage('syntax') {
          steps {
            sh 'ruby -c **/*.rb'
          }
        }
      }
    }
  }
}