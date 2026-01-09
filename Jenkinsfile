pipeline {
    agent none

    stages {

        stage('Checkout') {
            agent any
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'npm run build'
            }
        }
    }
}
