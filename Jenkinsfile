pipeline {
  agent {
    docker {
      image 'eclipse-temurin:11.0.13_8-jdk-focal'
      reuseNode true
    }

  }
  stages {
    stage('java -version') {
      steps {
        sh '''java -version
javac -version'''
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