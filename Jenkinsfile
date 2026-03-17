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
                branch 'dev'
            }
            steps {
                sh 'echo Deploying in dev'
            }
        }
        post{
            success {
                echo "Multibranch pipeline is successful"
            }
            failure {
                echo "Multibranch pipeline is a failure"
            }
        }

    }
}
