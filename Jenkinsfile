pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'This is the blue Pipeline'
        sleep 10
      }
    }

    stage('Test') {
      steps {
        warnError(message: 'Executing First Py failed') {
          sh 'python ~/PyScripts/SuccessFull.py'
        }

        warnError(message: 'Second Py failed') {
          sh 'python ~/PyScripts/Failed.py'
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy succeeded'
      }
    }

  }
}