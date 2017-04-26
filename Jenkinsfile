pipeline {
  agent {
    docker {
      image 'ruby:2.1.2'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh '''ruby -v
pwd
which bundle
bundle install
bundle exec rspec spec/*'''
      }
    }
  }
  environment {
    COVERALLS_SERVICE_NAME = 'jenkins'
    COVERALLS_ENDPOINT = 'https://enterprise-demo-2.coveralls.io'
    COVERALLS_REPO_TOKEN = 'k80tTMALlmaQOlMs23SvZDavemORnsiSi'
  }
}