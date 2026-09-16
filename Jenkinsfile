pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/gokul142006/agilelab1.git'
            }
        }
        stage('Generate Report') {
            when {
                branch 'main'
            }
            steps {
                bat 'python app.py'
            }
        }
        stage('Archive Report') {
            when {
                branch 'main'
            }
            steps {
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
