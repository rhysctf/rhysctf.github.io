pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Checkout code from Git
                git 'https://github.com/rhysctf/rhysctf.github.io'
                
                // Build using Maven
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run automated tests
                sh 'mvn test'
            }
        }

        stage('Quality Analysis') {
            steps {
                // Run SonarQube analysis
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy artifacts to staging or production
                // (This stage can be added based on your project's deployment needs)
            }
        }
    }

    post {
        success {
            // Send notifications for successful build
            echo "test success"
        }
        failure {
            // Send notifications for build failure
            echo "test fail"
        }
    }
}