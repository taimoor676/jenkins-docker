pipeline {
    agent any

    environment {
        DOCKER_COMPOSE_FILE = "docker-compose.yml"  // Adjust if your docker-compose file has a different name or location
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    echo "Checking out code from Git"
                }
                checkout scm // This checks out the repository configured in the Jenkins job
            }
        }

        stage('Build and Run with Docker Compose') {
            steps {
                script {
                    echo "Running Docker Compose"
                    sh """
                         docker-compose down || true
                          docker-compose up --build -d
                    """
                }
            }
        }
    }
}
