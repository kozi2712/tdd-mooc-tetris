pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/kozi2712/tdd-mooc-tetris']]])
            }
        }
        stage('Build') {
            steps {
              nodejs('Node20'){                  
                    sh 'npm install'
                }
            }
        }
        stage('Run tests') {
            steps {
                nodejs('Node20'){
                sh 'npm run test'
                }
            }
        }
    }
}
