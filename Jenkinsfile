pipeline {
  agent any
  stages {
    stage('build & unit tests') {
      steps {
        sleep(time: 1, unit: 'SECONDS')
        node(label: 'build')
      }
    }
    stage('static-analysis') {
      steps {
        sleep(time: 1, unit: 'SECONDS')
        node(label: 'build')
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