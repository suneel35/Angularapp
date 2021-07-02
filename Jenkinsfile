#!groovy
node {
        stage('checkout') {
             git branch: 'main', url: 'https://github.com/suneel35/Angularapp.git'  
            }
        stage('Docker Image') {
            sh 'docker build -t angular .'
        }
        stage('docker run') {
            
            sh 'docker rm -f angularapp'
            sh 'docker run -d -it -p 80:80/tcp --name angularapp angular'        
        }
        post { 
        always { 
            cleanWs()
        }
    }
    }
