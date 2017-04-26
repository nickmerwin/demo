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
    stage('Coveralls') {
      steps {
        sleep 10
        sh 'ruby -r json -e "res = JSON.parse %x(curl -k https://enterprise-demo-2.coveralls.io/github/nickmerwin/demo.json); exit res[\'coverage_change\'] >= 0 ? 0 : 1"'
      }
    }
  }
  environment {
    COVERALLS_SERVICE_NAME = 'jenkins-enterprise'
    COVERALLS_ENDPOINT = 'https://enterprise-demo-2.coveralls.io'
    COVERALLS_REPO_TOKEN = 'k80tTMALlmaQOlMs23SvZDavemORnsiSi'
    CI = 'true'
    CI_BRANCH = '$BRANCH_NAME'
  }
}