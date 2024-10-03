pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'gcc -o jobb1 jobb1.c'  // Kompilera jobb1.c
            }
        }

        stage('Test') {
            steps {
                sh 'gcc -o test_jobb1 test_jobb1.c -lcunit'  // Kompilera 
och kör tester
                sh './test_jobb1'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
        success {
            echo 'Build and tests succeeded'
        }
        failure {
            echo 'Build or tests failed'
        }
    }
}

