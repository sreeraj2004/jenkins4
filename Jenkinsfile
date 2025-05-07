pipeline {
    agent any

    triggers {
        pollSCM 'H/3 * * * *'
    }

    stages {
        stage('Clone'){
             steps {
                git url: '', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                script {
                    echo "Building Docker image..."
                    // Build Docker image from Dockerfile
                    bat 'docker build -t my-image-name .'
                    
                    echo "Running Docker container..."
                    // Run Docker container (detached mode)
                    bat 'docker run -d --name my-container -p 8080:80 my-image-name'
                }
            }
        }

        stage('Test') {
            steps {
                echo "test stage"
            }
        }

        stage('Deploy') {
            steps {
                echo "deploy stage"
            }
        }
    }
}