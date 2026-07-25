pipeline {
    agent any
    
    environment {
        APP_NAME = "Test-App"
        APP_VERSION = "1.0.0"
        APP_ENV = "dev"
    }

    stages {
        stage("Build") {
            steps {
                echo "Building Application..."
                echo "Building App with name ${APP_NAME}"
                echo "App version is ${APP_VERSION}"
                
                // Simulate failure if needed
                sh 'exit 0'   // change to exit 1 to test failure
            }
        }
        
        stage("Test") {
            steps {
                echo "Testing Application..."
                sh 'echo "Running tests..."'
            }
        }
        
        stage("Deploy") {
            steps {
                echo "Deploying Application..."
                sh 'echo "Deploy complete"'
            }
        }
    }

    post {
        success {
            echo "Pipeline is successful"
        }
        failure {
            echo "Pipeline failed"
        }
        always {
            echo "Cleanup: clearing workspace and logs..."
            cleanWs()   // Jenkins built-in step to clear workspace
            sh 'rm -rf /var/log/myapp/* || true'  // example log cleanup
        }
    }
}
