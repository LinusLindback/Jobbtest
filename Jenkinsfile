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
                // Ändra filnamnet till något annat än "jobb1"
                sh 'gcc -o jobb1_executable main.c'  // Kompilera main.c 
            }
        }

        stage('Test') {
            steps {
                sh 'gcc -o test_jobb1 test_jobb1.c -lcunit'  // Kompilera 
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

