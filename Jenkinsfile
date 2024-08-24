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
        // stage('Building Image') {
        //     steps {
        //         script {
        //             dockerImage = docker.build imageName
        //         }
        //     }
        // }
        // stage('Deploy Image') {
        //     steps {
                
        //     }
        // }
    }
}
