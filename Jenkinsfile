pipeline {
    agent any

    environment {
        PATH = "C:\\maven\\bin;${env.PATH}"  // Corrected the backslashes
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'mvn clean package'  // Correct use of bat
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
                bat 'echo Running code analysis'  // Replace with actual analysis command
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                bat 'echo Running security scan'  // Replace with an actual security tool command
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                bat 'echo Deploying app to staging'  // Replace with actual deploy command
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                bat 'echo Deploying app to production'  // Replace with actual deploy command
            }
        }
    }

    post {
        success {
            echo "✅ Build Successful!"
        }
        failure {
            echo "❌ Build Failed!"
        }
    }
}
