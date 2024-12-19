pipeline {
    agent any  // Correct syntax for specifying an agent

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/sarath0750/java.git', branch: 'main' // Specify branch if necessary
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh './mvnw clean install'  // Ensure `mvnw` is executable in your repo
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './mvnw test'  // Runs the tests
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deploy commands here
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}
