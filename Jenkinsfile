pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                build 'PES1UG21CS011-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                // Intentionally causing an error in the Test stage
                script {
                    // This command will intentionally fail
                    sh 'false'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
        }
    }
    
    post {
        failure {
            error 'Pipeline Failed'
        }
    }
}
