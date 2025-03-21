pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'mvn clean package'  // Use 'bat' instead of 'sh'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                bat 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality...'
                bat 'echo Running code analysis'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                bat 'echo Running security scan'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                bat 'echo Deploying app to staging'
            }
        }
    }

    post {
        success {
            echo "Build Successful!"
        }
        failure {
            echo "Build Failed!"
        }
    }
}
