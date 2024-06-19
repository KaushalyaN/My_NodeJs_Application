pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                git 'https://github.com/KaushalyaN/My_NodeJs_Application'
            }
        }
        
        stage('Build') {
            steps {
                // Install dependencies
                sh 'npm install'
                
                // Build the application
                sh 'npm run build'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                sh 'npm test'
                
                // Run linter
                sh 'npm run lint'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application
                // Start the Node.js server
                sh 'node app.js &'
                
                // Note: In production, consider using process managers like PM2 for Node.js apps.
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful!'
            // You can add additional actions on success, such as notifications
        }
        failure {
            echo 'Deployment failed!'
            // You can add actions to take on failure, such as sending notifications or rolling back changes
        }
    }
}

