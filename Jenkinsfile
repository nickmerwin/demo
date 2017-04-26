pipeline {
  agent {
    docker {
      image 'rtyler/rvm:2.3.0'
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