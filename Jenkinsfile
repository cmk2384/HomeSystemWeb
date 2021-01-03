pipeline {
  agent {
    node {
      label 'bluejenkins'
    }

  }
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

        sh 'python ~/PyScripts/SuccessFull.py'
        mail(subject: 'Jenkins Succeeded', body: 'Jenkins Test with Label has been finished successful', from: 'Jenkins', to: 'c_merkl@gmx.net')
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy succeeded'
      }
    }

  }
}