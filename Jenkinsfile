pipeline {
    jenkins-agent
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/sarath0750/java.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh './mvnw clean install'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './mvnw test'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deploy commands here
            }
        }
    }
}

