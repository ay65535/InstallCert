pipeline {
  agent any
  stages {
    stage('java -version') {
      parallel {
        stage('java -version') {
          steps {
            sh '''java -version
javac -version'''
          }
        }

        stage('java -version (pwsh)') {
          steps {
            powershell 'java -version'
            bat 'javac -version'
          }
        }

      }
    }

    stage('ls') {
      steps {
        sh 'ls -l'
      }
    }

    stage('javac') {
      steps {
        sh 'javac ./InstallCert.java'
      }
    }

  }
}