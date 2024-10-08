pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Kompilera main.c till en körbar fil kallad "hello"
                sh 'gcc -o hello main.c'
            }
        }

        stage('Run') {
            steps {
                // Kör den kompilerade filen "hello"
                sh './hello'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
        success {
            echo 'Build and run succeeded'
        }
        failure {
            echo 'Build or run failed'
        }
    }
}

