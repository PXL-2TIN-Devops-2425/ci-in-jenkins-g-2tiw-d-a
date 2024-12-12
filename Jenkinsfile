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
        stage('Unit Test') {
            steps {
                script {
                    sh 'npm test'
                    }
            junit 'junit.xml' 
            }
        }
        stage('Create Bundle') {
            steps {
                script {
                    sh '''
                        mkdir -p bundle
                        cp -r public app.js server.js routes.js package.json package-lock.json bundle/
                        cd bundle
                        zip -r ../bundle.zip .
                    '''
                }
                archiveArtifacts artifacts: 'bundle.zip', fingerprint: true
            }
        }
    }
    post {
        failure {
            script {
                def timestamp = new Date().format("yyyy-MM-dd HH:mm:ss")
                sh "echo 'pipeline poging faalt op ${timestamp}' >> ~/jenkinserrorlog"
            }
        }
        success {
            echo 'Pipeline completed successfully.'
        }
    }
}
