pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    echo "Building Docker image for branch: ${env.BRANCH_NAME}..."
                    bat """
                    docker build -t python-app:%BRANCH_NAME% .
                    """
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    echo "Running Docker container for branch: ${env.BRANCH_NAME}..."
                    bat """
                    docker run --rm python-app:%BRANCH_NAME%
                    """
                }
            }
        }
    }
}
