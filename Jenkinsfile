pipeline {
  agent any
  stages {
    stage('java -version') {
      parallel {
        stage('java -version') {
          agent {
            docker {
              image 'eclipse-temurin:11.0.13_8-jdk-focal'
            }

          }
          steps {
            sh '''java -version
javac -version'''
          }
        }

        stage('java -version (pwsh)') {
          steps {
            bat 'java -version'
            bat 'javac -version'
          }
        }

      }
    }

    stage('ls') {
      parallel {
        stage('ls') {
          agent {
            docker {
              image 'eclipse-temurin:11.0.13_8-jdk-focal'
            }

          }
          steps {
            sh 'ls -l'
          }
        }

        stage('gci') {
          steps {
            powershell(script: 'gci', encoding: 'utf-8')
          }
        }

      }
    }

    stage('javac') {
      parallel {
        stage('javac') {
          agent {
            docker {
              image 'eclipse-temurin:11.0.13_8-jdk-focal'
            }

          }
          steps {
            sh 'javac ./InstallCert.java'
          }
        }

        stage('javac (pwdh)') {
          steps {
            powershell 'javac ./InstallCert.java'
          }
        }

      }
    }

  }
  parameters {
    choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
  }
}