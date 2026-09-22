pipeline {
    environment {
        QODANA_TOKEN=credentials('qodana-token')
        QODANA_ENDPOINT='https://qodana.cloud'
    }
    agent {
        docker {
            args '''
              -v "${WORKSPACE}":/data/project
              --entrypoint=""
              '''
            image 'jetbrains/qodana-jvm:2026.1'
        }
    }
    stages {
        stage('Qodana') {
            steps {
                sh '''qodana'''
            }
        }
    }
}
