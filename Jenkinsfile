pipeline {
    agent none

        stages {
        stage('Clean Workspace') {
            agent any
            steps {
                cleanWs()
           }
        }
        stage('Checkout') {
            agent any
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '-u root'
                       }
            }
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'npm install'
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '-u root'
                       }
            }
            steps {
                sh 'npm run build'
            }
        }
    }
}
