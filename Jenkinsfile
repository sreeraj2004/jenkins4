pipeline {
    agent any

    triggers {
        pollSCM 'H/3 * * * *'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building Docker image..."
                    bat 'docker build -t my-image-name .'

                    echo "Running Docker container..."
                    bat 'docker run -d --name my-container -p 8001:80 my-image-name'
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
