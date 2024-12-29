pipeline {
    agent any
    stages {
        stage ('Pull Github repo') {
            steps {
                git branch: 'main',
                credentialsId: 'GithubToken',
                url: 'https://github.com/22127300/project3-mmtnc.git'
            }
        }
        stage ('Build and push to DockerHub') {
            steps {
                withDockerRegistry(credentialsId: 'DockerhubToken', url: 'https://index.docker.io/v1/') {
                    bat 'docker build -t 22127025/devops-mmtnc:latest .'
                    bat 'docker push 22127025/devops-mmtnc:latest'
                }
            }
        }
    }
}