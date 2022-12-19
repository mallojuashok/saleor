pipeline{
    agent any
    stages {
        stage('GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/mallojuashok/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t ashokachary/saleor:DEV .'
            }
        }
        stage('docker image push to registry') {
            steps {
                sh 'docker image push ashokachary/saleor:DEV '
            }
        }
}
}