pipeline {
    agent any
    stages {
      stage('build') {
        steps {
          sh 'npm --version'
          sh 'echo "Building"'
          sh '''
              echo "Multiline shell steps works too"
              ls -lah
          '''
        }
      }
      stage('test') {
        steps {
          sh 'echo "Testing"'
        }
      }
      stage('deploy - staging') {
        steps {
          sh 'echo "Deploy - Staging"'
        }
      }
      stage('sanity check') {
        steps {
          input 'Does this look ok?'
        }
      }
      stage('deploy - production') {
        steps {
          sh 'echo "Deploy - Production"'
        }
      }
    }
    post {
      always {
        echo 'One way or another, I have finished'
        deleteDir() /* clean up our workspace */
      }
      success {
        echo 'I succeeeded!'
      }
      unstable {
        echo 'I am unstable :/'
      }
      failure {
        echo 'I failed :('
      }
      changed {
        echo 'Things were different before...'
      }
    }
}