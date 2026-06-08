pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
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
        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarScanner'
                    withSonarQubeEnv('SonarQube') {
                        bat """
                        ${scannerHome}\\bin\\sonar-scanner.bat
                        """
                    }
                }
            }
        }
    }
}
