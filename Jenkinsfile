pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Get Repos') {
          steps {
            echo 'Hello World'
          }
        }
        stage('Build') {
          steps {
            echo 'Build thing'
          }
        }
        stage('Unit Test') {
          steps {
            echo 'ack'
          }
        }
        stage('Create Artifacts') {
          steps {
            sleep 1
          }
        }
      }
    }
    stage('Test') {
      parallel {
        stage('Deploy to X environment Server A') {
          steps {
            echo 'deploy this'
          }
        }
        stage('Deploy to X environment Server B') {
          steps {
            sleep 1
          }
        }
        stage('BVT Test') {
          steps {
            sleep 1
          }
        }
        stage('Approval') {
          steps {
            input 'Approval Needed'
          }
        }
      }
    }
    stage('Prod Stage ') {
      parallel {
        stage('Prod Stage Approval') {
          steps {
            echo 'test this'
          }
        }
        stage('Prod Stage') {
          steps {
            sleep 1
          }
        }
      }
    }
    stage('Prod Deployment') {
      parallel {
        stage('Prod Deployment Approval') {
          steps {
            echo 'wait'
          }
        }
        stage('Prod Deploy') {
          steps {
            sleep 1
          }
        }
      }
    }
  }
}