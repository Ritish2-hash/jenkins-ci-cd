pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean package'  // Example for Java projects (use appropriate build tool)
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                sh 'mvn test'  // Example for running tests
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality...'
                sh 'sonar-scanner'  // Using SonarQube for static code analysis
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                sh 'snyk test'  // Example using Snyk for security analysis
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                sh 'scp target/app.jar user@staging-server:/app'  // Example deployment command
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                sh 'curl -X GET http://staging-server:8080/health'  // Example health check
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                sh 'scp target/app.jar user@production-server:/app'  // Example deployment command
            }
        }
    }

    post {
        success {
            mail to: 'developer@example.com',
                 subject: "Jenkins Build Successful",
                 body: "The build and deployment were successful."
        }
        failure {
            mail to: 'developer@example.com',
                 subject: "Jenkins Build Failed",
                 body: "The build or deployment failed. Check logs for details."
        }
    }
}
