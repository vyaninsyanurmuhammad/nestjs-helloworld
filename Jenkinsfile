pipeline {
    agent any
    tools { nodejs 'node' }
    stages {
        stage('Define Env') {
            steps {
                withCredentials([file(credentialsId: 'hello_world_env')]){
                    sh 'cp $WORKSPACE'
                }
            }
        }
        // stage('Install Dependencies') {
        //     steps {
        //         sh 'npm install'
        //     }
        // }
        // stage('Tests') {
        //     steps {
        //         sh 'npm run test'
        //     }
        // }
        // stage('Check Docker') {
        //     steps {
        //         sh 'docker --version'
        //     }
        // }
        // stage('Building Image') {
        //     steps {
        //         sh 'docker build . -t vyaninsyanurmuhammad/hello_world:latest'
        //     }
        // }
        // stage('Push Image') {
        //     steps {
        //         withCredentials([usernamePassword(credentialsId: 'dockerHubVyan', passwordVariable: 'dockerHubVyanPassword', usernameVariable: 'dockerHubVyanUser')]) {
        //             sh "docker login -u ${env.dockerHubVyanUser} -p ${env.dockerHubVyanPassword}"
        //             sh 'docker push vyaninsyanurmuhammad/hello_world:latest'
        //         }
        //     }
        // }
        // stage('Deploy Image') {
        //     steps {
        //         sh 'docker stop hello_world || true'
        //         sh 'docker rm hello_world || true'
        //         sh 'docker run -d --name hello_world -p 8001:8001 vyaninsyanurmuhammad/hello_world:latest'
        //     }
        // }
    }
}