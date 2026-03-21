pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Fetching code..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Starting build..."
                sh """
                    # Simple example: compile or package
                    # Replace with your actual build command
                    echo "Building project..."
                """
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh """
                    # Example: run basic unit test scripts
                    # Replace with your test runner
                    echo "Running tests..."
                """
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                sh """
                    # Example deploy script
                    # Replace with your real deployment command
                    echo "Deploying to environment..."
                """
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
