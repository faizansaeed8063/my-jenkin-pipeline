pipeline {
    agent any

    // Task 9: Adding Build Parameters
    parameters {
        string(name: 'PERSON', defaultValue: 'Faizan', description: 'Who is running this build?')
        choice(name: 'ENVIRONMENT', choices: ['Staging', 'Production', 'Testing'], description: 'Select the target environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Check to run the Test stage')
    }

    environment {
        APP_NAME = "MySecureApp"
    }

    stages {
        stage('Parameters Info') {
            steps {
                echo "Build triggered by: ${params.PERSON}"
                echo "Target Environment: ${params.ENVIRONMENT}"
            }
        }
        stage('Build') {
            steps {
                echo "Building ${env.APP_NAME} version ${env.BUILD_NUMBER}..."
            }
        }
        stage('Test') {
            when {
                expression { params.RUN_TESTS == true }
            }
            steps {
                echo "Running tests in ${params.ENVIRONMENT} environment..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying to ${params.ENVIRONMENT}..."
            }
        }
    }

    post {
        always {
            echo "Finished execution for ${params.PERSON}"
        }
    }
}
