pipeline {
    agent any
    tools { nodejs 'Node' }

    stages {
        stage('Build') {
            steps {
                dir('landing-page') {       
                    echo 'Installing dependencies and building React app...'
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Test') {
            steps {
                dir('landing-page') {
                    echo 'Running tests...'
                    sh 'npx vitest run'
                }
            }
        }

        stage('Deploy') {
            steps {
                dir('landing-page') {
                    echo 'Deploying React app...'
                   
                }
            }
        }
    }

    post {
        always { echo 'Cleaning up...' }
        success { echo 'Pipeline succeeded!' }
        failure { echo 'Pipeline failed!' }
    }
}
