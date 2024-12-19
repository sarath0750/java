pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code from the repository...'
                // Checkout the repository (Jenkins automatically checks out code by default)
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Run the Maven build using the wrapper in the 'test4' folder
                sh './test4/mvnw clean install'  // Adjusted path to mvnw in the test4 folder
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // Add test commands if you want to run tests
                sh './test4/mvnw test'  // Example test command, adjust as needed
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment steps here if needed (e.g., deploy to a server or cloud)
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check the logs for more details.'
        }
    }
}
