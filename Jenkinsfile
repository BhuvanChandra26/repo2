pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out source code"
                checkout scm
            }
        }

        stage('Dev - Compile') {
            steps {
                echo "DEV: Compiling Hello.java"
                sh '''
                    set -e
                    javac Hello.java
                '''
            }
        }

        stage('Dev - Run') {
            steps {
                echo "DEV: Running app (prints Hello, World!)"
                sh 'java Hello'
            }
        }

        stage('Test - Sanity') {
            steps {
                echo "TEST: Verifying output"
                sh '''
                    set -e
                    OUT=$(java Hello)
                    echo "Output: $OUT"
                    if [ "$OUT" != "Hello, World!" ]; then
                      echo "Unexpected output in TEST stage"
                      exit 2
                    fi
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "DEPLOY: Simulating deploy (running app again)"
                sh 'java Hello'
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished (Dev → Test → Deploy)."
        }
    }
}
