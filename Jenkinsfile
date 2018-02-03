pipeline {
  agent {
    node {
      label 'GoToThisNode'
    }
    
  }
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
          agent {
            node {
              label 'GoToThisNodeA'
            }
            
          }
          steps {
            sleep 1
            echo 'Run Job To deploy this thing to A'
          }
        }
        stage('Deploy to Test Environment Server B') {
          agent {
            node {
              label 'GoToThisNodeB'
            }
            
          }
          environment {
            custom_variable = '1'
          }
          steps {
            sleep 1
            echo 'Run job to deploy this thing to B'
          }
        }
        stage('Publish to Database') {
          steps {
            sleep 1
            echo 'Publish if needed'
          }
        }
      }
    }
    stage('BVT Test') {
      agent any
      environment {
        TransformSomething = '1'
      }
      steps {
        sleep 1
        echo 'RunTestsJob'
      }
    }
    stage('Approval to Stage') {
      steps {
        sleep 1
        input 'Wait for Someone to Approve'
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
          when{
        branch 'master'
    }
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
  environment {
    TransformSomething = '1'
  }
}
