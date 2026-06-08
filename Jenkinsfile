pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/Twinkle-priya/kanban-react-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'SonarQube stage placeholder (configure later)'
                // If you configure Sonar later, you will replace this
                // with withSonarQubeEnv + scanner command
            }
        }

        stage('Quality Gate') {
            steps {
                echo 'Quality Gate placeholder'
            }
        }
    }

    post {
        always {
            echo 'Cleaning workspace...'
            // Optional but recommended on Windows
            cleanWs()
        }

        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
