pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/mallojuashok/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t ashokacharymalloju/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push ashokacharymalloju/saleor:DEV'
            }
        }
    }
}