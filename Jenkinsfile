pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm // This works only if SCM is configured in the job
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }
    }

    post {
        success {
            echo 'Build, test, and deploy succeeded!'
        }
        failure {
            echo 'Build, test, or deploy failed!'
        }
        always {
            echo 'Pipeline completed.'
        }
    }
}
