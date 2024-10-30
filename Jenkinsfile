pipeline {
    agent any

    stages {
        
        // Checkout source code from a simple Git repository
        stage('Checkout') {
            steps {
                // Replace with any public repository or a sample repo you own
                git 'https://github.com/example/repo.git'
            }
        }

        // Build the application
        stage('Build') {
            steps {
                // This example assumes a simple Java project with Gradle
                echo 'Building application...'
                sh './gradlew build'
            }
        }

        // Run unit tests
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test'
            }
        }

        // Deploy (for this example, we’ll just echo deployment success)
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Placeholder for actual deployment commands, e.g., copying files or invoking scripts
            }
        }
    }

    post {
        // Mark the build as successful or failed in Jenkins logs
        always {
            echo 'Cleaning up workspace...'
            deleteDir() // Clean up the workspace after each build
        }
        
        success {
            echo 'Build completed successfully!'
        }
        
        failure {
            echo 'Build failed. Check logs for details.'
        }
    }
}
