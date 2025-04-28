pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // You can add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }

    post {
        success {
            mail to: 'recipient@example.com',
                 subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Good news! Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed successfully.\nCheck it here: ${env.BUILD_URL}"
        }
        failure {
            mail to: 'recipient@example.com',
                 subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Something went wrong in Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'.\nCheck the logs: ${env.BUILD_URL}"
        }
    }
}
