pipeline {
    agent any

    environment {
        // Define environment variables if needed
        WP_DB_HOST = 'your_db_host'
        WP_DB_NAME = 'your_db_name'
        WP_DB_USER = 'your_db_user'
        WP_DB_PASSWORD = 'your_db_password'
        WP_URL = 'http://your-wordpress-url.com'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                script {
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                // Your build steps if any
            }
        }

        stage('Deploy') {
            steps {
                // Deploy WordPress
                script {
                    sh "docker-compose -f docker-compose.yml up -d"
                }
            }
        }

        stage('Test') {
            steps {
                // Your test steps if any
            }
        }

        stage('Cleanup') {
            steps {
                // Cleanup steps if needed
            }
        }
    }

    post {
        success {
            // Actions to perform on success
            echo "WordPress deployed successfully!"
        }

        failure {
            // Actions to perform on failure
            echo "Deployment failed. Check logs for details."
        }
    }
}

