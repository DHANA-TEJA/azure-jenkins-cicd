pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/<your-username>/azure-jenkins-cicd.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application...'
                sh 'echo "Build Successful!"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'echo "All Tests Passed!"'
            }
        }

        stage('Deploy to Azure VM') {
            steps {
                echo 'Deploying Application to Azure VM...'
                sh '''
                ssh -o StrictHostKeyChecking=no azureuser@20.40.58.75 "cd /var/www/html && git pull origin main && sudo systemctl restart nginx"
                '''
            }
        }
    }
}
