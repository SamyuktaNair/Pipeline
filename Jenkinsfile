pipeline {
    agent any

    tools {
        nodejs 'Node'  
    }


    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies and building React app...'
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test -- --watchAll=false'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying React app...'
                //hi
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
