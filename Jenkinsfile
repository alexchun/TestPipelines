pipeline {
  agent any
  stages {
    stage('DEV') {
      parallel {
        stage('Build') {
          steps {
            echo 'Hello World'
          }
        }
        stage('Deploy') {
          steps {
            echo 'Build thing'
          }
        }
        stage('Test') {
          steps {
            echo 'ack'
          }
        }
      }
    }
    stage('Test') {
      parallel {
        stage('Test1') {
          steps {
            echo 'deploy this'
          }
        }
        stage('Deploy2') {
          steps {
            sleep 1
          }
        }
        stage('Test3') {
          steps {
            sleep 1
          }
        }
      }
    }
    stage('Prod') {
      parallel {
        stage('Prod') {
          steps {
            echo 'test this'
          }
        }
        stage('Prod Test') {
          steps {
            sleep 1
          }
        }
      }
    }
  }
}