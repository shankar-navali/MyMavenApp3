pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the project repository
                git 'https://github.com/shankar-navali/MyMavenApp3.git'  // Replace with your repository URL
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the project using Maven
                    sh 'mvn clean install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run unit tests using Maven Surefire Plugin
                    sh 'mvn test'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // If you want to execute the app (useful for testing or deployment)
                    // Example: Run the main class using Maven exec plugin
                    sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps here, for example, if you're deploying to a server or cloud
                    echo 'Deploying application...'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment were successful.'
        }

        failure {
            echo 'Build or deployment failed.'
        }
    }
}
