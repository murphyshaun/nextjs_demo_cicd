pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/murphyshaun/nextjs_demo_cicd.git'
                sh 'docker ps'
            }
        }

        stage('Docker Registry') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub-test', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t leeshaun/nextjs-cicd:v10 .'
                    sh 'docker push leeshaun/nextjs-cicd:v10'
                }
            }
        }

    }
}