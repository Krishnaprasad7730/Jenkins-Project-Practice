pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Building branch"
                sh 'docker build -t test-app .'
            }
        }

        stage('Test') {
            when {
                branch 'dev'
            }
            steps {
                echo "Running tests in dev"
            }
        }

        stage('Deploy') {
            when {
                branch 'prod'
            }
            steps {
                echo "Deploying in prod"
            }
        }

    }

    post {
        success {
            echo "Multibranch pipeline is successful"
        }
        failure {
            echo "Multibranch pipeline is failure"
        }
    }
}
