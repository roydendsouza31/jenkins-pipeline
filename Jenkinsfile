pipeline {
    agent any

    stages {

        stage('Clean Workspace') {
            steps {
                script {
                    if (fileExists('jenkins-pipeline')) {
                    sh 'rm -rf jenkins-pipeline'
                    }
                }
            }
        }

        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning repository...'
                    sh 'git clone "https://github.com/roydendsouza31/jenkins-pipeline.git"'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    echo 'Building Docker image...'
                    sh 'docker build -t testimage:latest .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    echo 'Running Docker container...'
                    sh 'docker run -d --name testcontainer -p 5000:5000 testimage:latest'
                }
            }
        }
    }
}
