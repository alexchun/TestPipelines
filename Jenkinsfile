pipeline {
  agent any
  stages {
    stage('Build Project') {
      steps {
        echo 'Send Notification'
        echo 'Get Repo'
        echo 'Get Nuget'
        echo 'Build Project'
        echo 'Run BVT'
        echo 'Publish Artifacts'
      }
    }
    stage('Approval to Deploy') {
      steps {
        sleep 1
      }
    }
    stage('Deploy to Test Environment') {
      parallel {
        stage('Deploy to Test Environment Server A') {
          steps {
            sleep 1
          }
        }
        stage('Deploy to Test Environment Server B') {
          steps {
            sleep 1
          }
        }
        stage('Publish to Database') {
          steps {
            sleep 1
          }
        }
      }
    }
    stage('BVT Test') {
      steps {
        sleep 1
      }
    }
    stage('Approval to Stage') {
      steps {
        sleep 1
      }
    }
    stage('Stage to Production') {
      parallel {
        stage('Stage to Production Server A') {
          steps {
            sleep 1
          }
        }
        stage('Stage to Production Server B') {
          steps {
            sleep 1
          }
        }
      }
    }
    stage('Approval to Deploy to Production') {
      steps {
        sleep 1
      }
    }
    stage('Deploy to Production Server A') {
      parallel {
        stage('Deploy to Production Server A') {
          steps {
            sleep 1
          }
        }
        stage('Deploy to Production Server B') {
          steps {
            sleep 1
          }
        }
      }
    }
  }
}