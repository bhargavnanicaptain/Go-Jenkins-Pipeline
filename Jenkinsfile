pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling source code...'
                checkout scm
            }
        }

        stage('Install Go') {
            steps {
                echo 'Checking Go installation...'
                sh 'go version || sudo apt install -y golang-go'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Go binary...'
                sh 'go build -o output main.go'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests (none yet)...'
                sh 'echo No tests configured yet.'
            }
        }

        stage('Run App') {
            steps {
                echo 'Running built app...'
                sh './output'
            }
        }
    }

    post {
        success {
            echo '✅ Build and Run Successful!'
        }
        failure {
            echo '❌ Build Failed.'
        }
    }
}
