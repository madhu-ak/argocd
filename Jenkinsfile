pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the specified GitHub repository
                git url: 'https://github.com/madhu-ak/argocd.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Navigate to the app directory and build the Docker image
                    dir('go-app') {
                        // Ensure Docker is running and build the image
                        sh 'docker build -t myapp .'
                    }
                }
            }
        }

        // Additional stages for testing, deployment, etc. can be added here
    }
}
