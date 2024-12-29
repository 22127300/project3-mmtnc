pipeline {
  agent any

  stages{
    stage ('Pull Github repository'){
      steps{
        git branch: 'main',
        url: 'https://github.com/22127300/project3-mmtnc.git'
      }
    }
    stage ('Build and push to DockerHub') {
      steps {
        withDockerRegistry(credentialsId: 'DockerHubToken', url: 'https://index.docker.io/v1/') {
          bat 'docker build -t 22127025/mmtnc-project3:latest .'
          bat 'docker push 22127025/mmtnc-project3:latest'
        }
      }
    }
  }
}