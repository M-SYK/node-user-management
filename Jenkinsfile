pipeline {
    agent any

    stages {
        stage('Clone repository and build') {
            steps {
                script {
                    git 'https://github.com/M-SYK/node-user-management.git'
                    sh 'cd node-user-management && npm install'
                }
            }
        }

        stage('Start Node.js application') {
            steps {
                script {
                    sh 'cd node-user-management && npm run server'
                }
            }
        }
    }
}

