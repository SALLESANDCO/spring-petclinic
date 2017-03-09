pipeline {
  agent any
  stages {
    stage('build & unit tests') {
        agent { label 'build'}
      steps {
        sleep(time: 1, unit: 'SECONDS')
      }
    }
    stage('static-analysis') {
        agent { label 'build'}
      steps {
        sleep(time: 1, unit: 'SECONDS')
      }
    }
    stage('acceptance-tests') { 
      steps {
	parallel chrome: {
          sleep(time: 1, unit: 'SECONDS')
          },
          edge: {
          sleep(time: 1, unit: 'SECONDS')
          },
          firefox: {
          sleep(time: 1, unit: 'SECONDS')
          }
      }
    }
    stage('staging') {
      steps {
        sleep(time: 1, unit: 'SECONDS')
      }
    }
    stage('manual-approval') {
      steps {
        input(message: 'On y va ?', id: 'approve')
      }
    }
    stage('deploy') {
      steps {
        sleep(time: 1, unit: 'SECONDS')
      }
    }
  }
}