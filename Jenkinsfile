pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            // Task 5: Only run this stage on the main branch
            when {
                branch 'main'
            }
            steps {
                echo 'Testing only on main branch'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    // Task 4: Post-build feedback
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
