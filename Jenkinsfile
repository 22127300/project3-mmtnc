pipeline {
    stages {
        stage ('Pull Github repo') {
            steps {
                git branch: 'main',
                credentialsId: 'GithubToken',
                url: 'https://github.com/22127300/project3-mmtnc.git'
            }
        }
    }
}