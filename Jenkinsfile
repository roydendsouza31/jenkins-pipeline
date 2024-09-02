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
                echo 'Cloning repository...'
                sh 'git clone https://github.com/roydendsouza31/jenkins-pipeline.git'
            }
        }
        // Other stages like Build Docker Image, Run Docker Container, etc.
    }
}
