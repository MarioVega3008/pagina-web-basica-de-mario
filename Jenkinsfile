pipeline {
    agent any
    
    stages {
        stage('Checkout Código') {
            steps {
                git branch: 'main', url: 'https://github.com/MarioVega3008/pagina-web-basica-de-mario.git'
            }
        }
        
        stage('Instalar Dependencias') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Compilar Aplicación') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Ejecutar Pruebas') {
            steps {
                sh 'npm test'
            }
        }
        
        stage('Empaquetar y Archivar') {
            steps {
                archiveArtifacts artifacts: 'dist/**', fingerprint: true
            }
        }
        
        stage('Despliegue') {
            steps {
                echo 'Desplegando la aplicación...'
                // Aquí puedes agregar comandos para desplegar en un servidor web como Apache, Nginx o Vercel
            }
        }
    }
    
    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build completed failed!'
        }
    }
}
