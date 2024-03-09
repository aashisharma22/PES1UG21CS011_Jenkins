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
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                becho 'Deploy'
            }
        }
    }
    
    post {
        failure {
            error 'Pipeline Failed'
        }
    }
}
