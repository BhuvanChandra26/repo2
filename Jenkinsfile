// pipeline {
//     agent any

//     environment {
//         SONAR_SCANNER = tool 'SonarScanner'
//     }

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building...'
//             }
//         }

//         stage('Sonar Scan') {
//             steps {
//                 withSonarQubeEnv('MySonarQube') {
//                     sh """
//                         ${SONAR_SCANNER}/bin/sonar-scanner \
//                         -Dsonar.projectKey=repo2 \
//                         -Dsonar.sources=. \
//                         -Dsonar.host.url=http://localhost:9000 \
//                         -Dsonar.login=sqp_9bb753cd51113b98c02e2515289241f5ed9f1486
//                     """
//                 }
//             }
//         }

//         stage('Quality Gate') {
//             steps {
//                 timeout(time: 2, unit: 'MINUTES') {
//                     waitForQualityGate abortPipeline: true
//                 }
//             }
//         }
//     }
// }



pipeline {
    agent any
    environment {
        SCANNER_HOME = tool 'SonarScanner'
    }


    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/BhuvanChandra26/repo2.git'
            }
        }

       stage('SonarQube Analysis') {
         steps {
           withSonarQubeEnv('SonarQube') {
            sh """
               ${SONAR_SCANNER}/bin/sonar-scanner \
                        -Dsonar.projectKey=repo2 \
                        -Dsonar.sources=. \
                        -Dsonar.host.url=http://localhost:9000 \
                        -Dsonar.login=sqp_9bb753cd51113b98c02e2515289241f5ed9f1486
            """
        }
    }
}
}}
