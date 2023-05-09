pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/murphyshaun/nextjs_demo_cicd.git'
            }
        }

        stage('Docker Registry') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub-test', url: 'https://hub.docker.com/') {
                    sh 'docker ps'
                    sh 'docker build -t leeshaun/nextjs-cicd:v10 .'
                    sh 'docker push leeshaun/nextjs-cicd:v10'
                }
            }
        }

    }
}