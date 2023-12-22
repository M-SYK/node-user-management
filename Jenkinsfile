pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Jenkins, GitHub deposundan kodu çekecek
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Projeyi derleme adımları
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                // Test adımları
                script {
                    sh 'npm test'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Uygulamayı istediğiniz bir ortama dağıtma adımları
                script {
                    sh 'npm run deploy'
                }
            }
        }
    }
}
