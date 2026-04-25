pipeline {
    agent any

    environment {
        APP_NAME = "MySecureApp"
    }

    stages {
        stage('Build') {
            steps {
                // Using a custom env variable
                echo "Starting Build for ${env.APP_NAME}"
                // Using built-in env variables
                echo "Running Build Number: ${env.BUILD_NUMBER}"
            }
        }
        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                echo "Testing on Job: ${env.JOB_NAME}"
            }
        }
        stage('Environment Info') {
            steps {
                // Accessing more built-in variables
                echo "--- Jenkins System Info ---"
                echo "Build URL: ${env.BUILD_URL}"
                echo "Node Name: ${env.NODE_NAME}"
                echo "Workspace Path: ${env.WORKSPACE}"
                echo "Branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying Build #${env.BUILD_NUMBER} to production..."
            }
        }
    }

    post {
        always {
            echo "Finished execution of ${env.JOB_NAME} build ${env.BUILD_NUMBER}"
        }
    }
}
