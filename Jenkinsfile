pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Test') {
            steps {
                echo "Testing branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying branch: ${env.BRANCH_NAME}"
            }
        }
    }

    post {
        success {
            echo "✅ Build Success for: ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ Build Failed for: ${env.BRANCH_NAME}"
        }
    }
}
