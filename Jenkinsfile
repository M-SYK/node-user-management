pipeline {
    agent any
    
    stages {
        stage('Clone repository and build') {
            steps {
                // Git repository'yi çekmek için
                git 'https://github.com/M-SYK/node-user-management.git'

                // Projeyi içine gidin ve gerekli bağımlılıkları yüklemek için
                dir('node-user-management') {
                    sh 'npm install'
                }
            }
        }

        stage('Start Node.js application') {
            steps {
                // Node.js uygulamasını başlatmak için
                dir('node-user-management') {
                    sh 'npm run server'
                }
            }
        }
    }
    
    post {
        success {
            // Başarılı bir şekilde tamamlandığında yapılacaklar
            echo 'Pipeline başarıyla tamamlandı. Uygulama Kubernetes üzerinde çalışıyor.'
        }
    }
}
