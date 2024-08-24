pipeline {
    agent any
    tools { nodejs 'node' }
    environment {
        dockerImage = 'vyaninsyanurmuhammad/hello_world'
    }
    stages {
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
        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Building Image') {
            steps {
               sh 'docker build . -t vyaninsyanurmuhammad/hello_world:latest'
            }
        }
        stage('Push') {
            steps {
                sh "docker login -u vyaninsyanurmuhammad -p A1F2I3N4Z5Aasd"
                sh 'docker push vyaninsyanurmuhammad/hello_world:latest'
            }
        }
        stage('Deploy Image') {
            steps {
                sh 'docker stop hello_world || true'
                sh 'docker rm hello_world || true'
                sh 'sudo docker run -d --name nodetodoapp -p 8001:8001 vyaninsyanurmuhammad/hello_world:latest'
            }
        }
    }
}
