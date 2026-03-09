pipeline {
    agent any

    tools {
        maven 'Maven 3.9.12'
    }

    options {
        timestamps()
    }

    environment {
        IMAGE_NAME = 'week7-calculator'
        TAG = 'latest'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/irakump/week7-calculator.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Docker Build') {
            steps {
                bat 'docker build -t %IMAGE_NAME%:%TAG% .'
            }
        }
    }
}
