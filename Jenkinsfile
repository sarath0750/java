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
                // List contents of test4 to confirm mvnw is found
                sh 'ls -l ./test4'
                // Run Maven build using the wrapper in the 'test4' folder
                sh './test4/mvnw clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                sh './test4/mvnw test'  // Adjust this based on your project
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
