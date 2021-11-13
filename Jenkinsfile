pipeline {
  agent none
  stages {
    stage('BuildAndTestwin') {
      parallel {
        stage('windows') {
          when {
            expression {
              params.PLATFORM == 'windows'
            }

          }
          steps {
            echo params.PLATFORM
          }
        }

        stage('linux') {
          when {
            expression {
              params.PLATFORM == 'linux'
            }

          }
          steps {
            echo params.PLATFORM
          }
        }

      }
    }

  }
  parameters {
    choice(name: 'PLATFORM', choices: ['windows', 'linux'], description: 'Run on specific platform')
  }
}