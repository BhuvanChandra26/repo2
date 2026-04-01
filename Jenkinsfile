pipeline {
    agent any

    environment {
        SONAR_SCANNER = tool 'SonarScanner'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Sonar Scan') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    sh """
                        ${SONAR_SCANNER}/bin/sonar-scanner \
                        -Dsonar.projectKey=my-project \
                        -Dsonar.sources=src \
                        -Dsonar.java.binaries=target \
                        -Dsonar.host.url=http://YOUR_SONAR_URL \
                        -Dsonar.login=YOUR_TOKEN
                    """
                }
            }
        }

        stage('Quality Gate') {
            steps {
                timeout(time: 2, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
