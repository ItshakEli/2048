pipeline {
  agent any
  stages {
    stage('prepare') {
      steps {
        sh 'ls'
        echo 'new message'
        sleep 10
      }
    }
    stage('parallel1') {
      parallel {
        stage('parallel1') {
          steps {
            echo 'task1'
          }
        }
        stage('task2') {
          steps {
            echo 'task2'
          }
        }
      }
    }
    stage('last') {
      steps {
        echo 'last'
        sh 'echo $ENV1'
      }
    }
  }
  environment {
    ENV1 = '1'
    ENV2 = '2'
  }
}