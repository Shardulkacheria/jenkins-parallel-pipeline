pipeline {
    agent any

    stages {
        stage('Parallel Builds for Branches') {
            parallel {
                stage('Build Login Service') {
                    when {
                        branch 'feature-login'
                    }
                    steps {
                        echo "Building LOGIN feature on branch: ${env.BRANCH_NAME}"
                    }
                }
                
                stage('Build Payment Service') {
                    when {
                        branch 'feature-payment'
                    }
                    steps {
                        echo "Building PAYMENT feature on branch: ${env.BRANCH_NAME}"
                    }
                }
            }
        }
    }

    post {
        success {
            echo "✅ Parallel Pipeline completed successfully for ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ Build failed for ${env.BRANCH_NAME}"
        }
    }
}
