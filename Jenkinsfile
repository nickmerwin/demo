pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'bundle exec rspec'
      }
    }
  }
  environment {
    COVERALLS_SERVICE_NAME = 'jenkins'
    COVERALLS_ENDPOINT = 'https://enterprise-demo-2.coveralls.io'
    COVERALLS_REPO_TOKEN = 'k80tTMALlmaQOlMs23SvZDavemORnsiSi'
  }
}