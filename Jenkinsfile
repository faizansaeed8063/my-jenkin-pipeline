pipeline {
    agent any

    // Task 8: Defining Environment Variables
    environment {
        APP_NAME = "MySecureApp"
        APP_VERSION = "1.0.0"
        BUILD_ENV = "Staging"
    }

    stages {
        stage('Build') {
            steps {
                echo "Building ${env.APP_NAME}..."
            }
        }
        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                // Using variables in echo statements
                echo "Testing ${env.APP_NAME} Version ${env.APP_VERSION}"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying to ${env.BUILD_ENV} environment..."
            }
        }
        // Verification Stage for Variables
        stage('Info') {
            steps {
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Branch Name: ${env.BRANCH_NAME}"
            }
        }
    }

    post {
        always {
            echo "Pipeline execution finished for ${env.APP_NAME}"
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
