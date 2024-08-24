pipeline {
    agent any
    tools { nodejs 'node' }
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
                sh 'sudo docker build . -t vyaninsyanurmuhammad/hello_world:latest'
            }
        }
        stage('Push') {
            steps {
                sh 'sudo docker login -u vyaninsyanurmuhammad -p A1F2I3N4Z5Aasd'
                sh 'sudo docker push vyaninsyanurmuhammad/hello_world:latest'
            }
        }
        stage('Deploy Image') {
            steps {
                sh 'sudo docker stop hello_world || true'
                sh 'sudo docker rm hello_world || true'
                sh 'sudo docker run -d --name hello_world -p 8001:8001 vyaninsyanurmuhammad/hello_world:latest'
            }
        }
    }
}
