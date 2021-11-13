pipeline {
  agent none
  stages {
    stage('BuildAndTest') {
      parallel {
        stage('windows') {
          when {
            expression {
              params.PLATFORM == 'node1'
            }

          }
          steps {
            echo params.PLATFORM
            powershell(script: 'gci', encoding: 'UTF-8')
          }
        }

        stage('linux') {
          agent {
            docker {
              image 'eclipse-temurin:11.0.13_8-jdk-focal'
            }

          }
          when {
            expression {
              params.PLATFORM == 'docker'
            }

          }
          steps {
            echo params.PLATFORM
            sh 'ls'
          }
        }

      }
    }

  }
  parameters {
    choice(name: 'SELECT_NODE', choices: ['node1', 'node2', 'node3', 'node4', 'node5', 'node6', 'docker'], description: 'Select the node to be deployed to.')
  }
}