node {
    stage('Checkout') {
        echo 'Cloning repository...'
        checkout scm
    }

    stage('Set up NodeJS') {
        echo 'Setting up NodeJS environment...'
        def nodeHome = tool name: 'Node', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${nodeHome}/bin:${env.PATH}"
    }

    stage('Build') {
        dir('landing-page') {
            echo 'Installing dependencies and building React app...'
            sh 'npm install'
            sh 'npm run build'
        }
    }

    stage('Test') {
        dir('landing-page') {
            echo 'Running Vitest tests...'
            // If you want to allow pipeline success even with no tests, add "|| true" at the end
            sh 'npx vitest run'
        }
    }

    stage('Deploy') {
        echo 'Deploying application... (placeholder)'
        // Example future step:
        // sh 'npm run deploy'
    }

    stage('Cleanup') {
        echo 'Cleaning up...'
    }

    echo '✅ Pipeline completed successfully!'
}

