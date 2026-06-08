pipeline {
    agent any

    tools {
        nodejs 'Node18'
    }

    environment {
        NODE_OPTIONS = "--openssl-legacy-provider"
    }

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/Twinkle-priya/kanban-react-app.git', branch: 'master'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build React App') {
            steps {
                bat 'npm run build'
            }
        }
    }
}
