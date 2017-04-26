pipeline {
  agent any
  stages {
    stage('Setup') {
      steps {
        sh 'bundle --path "/tmp/gems"'
      }
    }
    stage('Build') {
      steps {
        sh 'bundle exec rspec spec/*'
      }
    }
  }
  environment {
    COVERALLS_SERVICE_NAME = 'jenkins-enterprise'
    COVERALLS_ENDPOINT = 'https://enterprise-demo-2.coveralls.io'
    COVERALLS_REPO_TOKEN = 'k80tTMALlmaQOlMs23SvZDavemORnsiSi'
    CI = 'true'
  }
}