pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code from the repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Debugging: print the current working directory
                sh 'pwd'
                // Debugging: list contents of the test4 folder to confirm mvnw is there
                sh 'ls -l ./test4'
                // Run the Maven build using the wrapper in the 'test4' folder
                sh './test4/mvnw clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // Example test command
                sh './test4/mvnw test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
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
