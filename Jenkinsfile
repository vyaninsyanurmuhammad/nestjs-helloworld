pipeline {
    agent any
    tools { nodejs 'node' }
    environment {
        imageName = 'vyaninsyanurmuhammad/hello-world'
        registryCredential = 'vyaninsyanurmuhammad'
        dockerImage = ''
    }
    stages {
        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Tests') {
            steps {
                sh 'npm run test'
            }
        }
        stage('Building Image') {
            steps {
                script {
                    dockerImage = docker.build imageName
                }
            }
        }
        stage('Deploy Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-creds') {
                        dockerImage.push("${env.BUILD_NUMBER}")
                    }
                }
            }
        }
    }
}
