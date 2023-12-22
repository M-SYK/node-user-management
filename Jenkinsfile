pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // GitHub repository'yi Jenkins'a çek
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Uygulama derlemesi (örneğin: npm install, mvn clean install)
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                // Uygulama testleri
                sh 'npm test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Uygulamayı Kubernetes üzerine dağıt
                sh 'kubectl apply -f kubernetes-deployment.yml'
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
