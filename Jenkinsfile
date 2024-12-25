pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "flask-app"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo/devops-project.git' // Replace with your repository URL
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${DOCKER_IMAGE} ."
                }
            }
        }
        stage('Run Tests') {
            steps {
                sh 'python -m unittest discover -s . -p "tests/test_*.py"'
            }
        }
    }
}
