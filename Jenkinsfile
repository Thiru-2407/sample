pipeline {
    agent any
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select the deployment environment')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: ' https://github.com/Thiru-2407/sample.git&#x27 ;
            }
        }
        stage('Generate Report') {
            steps {
                bat 'python app.py'
            }
        }
        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
        stage('Show Parameter') {
            steps {
                echo "Selected environment: ${params.ENVIRONMENT}"
            }
        }
        stage('Build for Environment') {
            steps {
                echo "Building the application for the ${params.ENVIRONMENT} environment..."
            }
        }
    }
}
