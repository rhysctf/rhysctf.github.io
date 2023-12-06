pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building...'
                    // Example: Use Maven for a Java project
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Testing...'
                    // Example: Run JUnit tests for a Java project
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deployment commands here
            }
        }
    }
}