pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'echo Building branch'
                sh 'docker build -t test-app .'
            }
        }

        stage('Test') {
            when {
                branch 'dev'
            }
            steps {
                sh 'echo Running tests in dev'
            }
        }

        stage('Deploy') {
            when {
                branch 'prod'
            }
            steps {
                sh 'echo Deploying in prod'
            }
        }

    }
}
