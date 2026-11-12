pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/playwright:v1.65.0-jammy'
            args '-u root --entrypoint='
        }
    }
    stages {
        stage('install dep') {
            steps {
                sh 'npm install'
            }
        }
        stage('Lancer le test test') {
            steps {
                sh ' npx playwright test'
            }
        }
    }
}