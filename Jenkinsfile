pipeline {
    agent any

    stages {
        stage('Start') {
            steps {
                echo "Pipeline Started"
            }
        }

        stage('Build') {
            steps {
                echo "Running Build Stage..."
            }
        }

        stage('Test') {
            steps {
                echo "Executing Tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Application..."
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished"
        }
    }
}
