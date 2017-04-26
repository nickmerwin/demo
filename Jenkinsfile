pipeline {
  agent {
    docker {
      image 'ruby:2.4.1-onbuild'
    }
    
  }
  stages {
    stage('Setup') {
      steps {
        sh 'bundle'
      }
    }
    stage('Build') {
      steps {
        sh 'bundle exec rake'
      }
    }
  }
  environment {
    COVERALLS_SERVICE_NAME = 'jenkins'
    COVERALLS_ENDPOINT = 'https://enterprise-demo-2.coveralls.io'
    COVERALLS_REPO_TOKEN = 'k80tTMALlmaQOlMs23SvZDavemORnsiSi'
  }
}