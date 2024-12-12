pipeline {
    agent any
    tools {
        nodejs 'TINnode-devops'
    }
    stages {
        stage('Fetching Source') {
            steps {
                script {
                    git branch: 'main',
                        url: 'git@github.com:adewandre/calculator-app-finished.git',
                        credentialsId: '8f791c44-e89e-4931-bd98-7486e7be9271'
                }
            }
        }
        stage('Install Dependencies') {
            steps { 
                sh 'npm install' 
            }
        }
    }
}
