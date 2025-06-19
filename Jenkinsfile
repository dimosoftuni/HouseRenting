pipeline {
    agent any

    stages {
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }

        stage('Build the project') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Run tests') {
            stage('Security Audit') {
                steps {
                    bat 'dotnet test'
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        }
    }
}
