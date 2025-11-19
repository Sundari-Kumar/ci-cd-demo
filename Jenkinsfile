pipeline {
    agent any

    tools {
        maven 'Maven3.9'   // Use the name you set in Jenkins Maven installation
        jdk 'JDK21'        // Use the name of your installed JDK
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/<your-username>/ci-cd-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building the Java project..."
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo "Running Tests..."
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                bat 'echo Deployment successful!'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executed successfully!'
        }
        failure {
            echo '❌ Pipeline failed.'
        }
    }
}
