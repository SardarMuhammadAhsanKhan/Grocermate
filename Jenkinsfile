pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/SardarMuhammadAhsanKhan/Grocermate.git'
      }
    }
    stage('Publish') {
      steps {
        publishHTML(target: [
          reportName: 'GrocerMate Site',
          reportDir: '.',
          reportFiles: 'index.html',
          keepAll: true,
          alwaysLinkToLastBuild: true
        ])
      }
    }
  }
}

