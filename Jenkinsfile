pipeline {
    parameters {
        choice(name: 'PLATFORM', choices: ['windows', 'linux'], description: 'Run on specific platform')
    }
    agent none
    stages {
        stage('BuildAndTest') {
            when { expression { params.PLATFORM == 'windows' } }
            echo 'windows'
        }
        stage('BuildAndTest') {
            when { expression { params.PLATFORM == 'linux' } }
            echo 'linux'
        }
    }
}
