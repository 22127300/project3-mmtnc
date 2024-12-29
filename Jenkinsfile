// pipeline {
//   agent any

//   stages{
//     stage ('Pull Github repository'){
//       steps{
//         git branch: 'main', credentialsId: '3844ce5f-c806-42bd-80fa-2aad0b4da120', url: 'https://github.com/22127300/project3-mmtnc.git'
//       }
//     }
//     stage ('Build and push to DockerHub') {
//       steps {
//         withDockerRegistry(credentialsId: 'dockerhubtoken', url: 'https://index.docker.io/v1/') {
//           bat 'docker build -t 22127025/mmtnc-project3:latest .'
//           bat 'docker push 22127025/mmtnc-project3:latest'
//         }
//       }
//     }
//   }
// }

pipeline {
    agent any

    environment {
        DOCKER_IMAGE = '22127025/mmtnc-project3:latest'
    }

    stages {
        stage('Pull GitHub Repository') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', 
                    credentialsId: '3844ce5f-c806-42bd-80fa-2aad0b4da120', 
                    url: 'https://github.com/22127300/project3-mmtnc.git'
            }
        }

        stage('Build and Push to DockerHub') {
            steps {
                echo 'Building Docker image...'
                withDockerRegistry(credentialsId: 'dockerhubtoken', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t 22127025/mmtnc-project3:latest .'
                    sh 'docker push 22127025/mmtnc-project3:latest'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for details.'
        }
    }
}
