pipeline {
    agent any
    stages {
      stage('build') {
        steps {
          sh 'npm --version'
          sh 'echo "Hello World"'
          sh '''
              echo "Multiline shell steps works too"
              ls -lah
          '''
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