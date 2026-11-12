pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/playwright:v1.65.0-jammy'
            args '-u root'
        }
    }
    stages {
        stage('Check version nodejs') {
            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }
        stage('install dep') {
            steps {
                sh 'npm install -g newman newman-reporter-htmlextra'
                sh 'newman --version'
            }
        }
        stage('Lancer le test') {
            steps {
                sh 'newman run ma_collection.json -e mon_env.json -r cli,htmlextra --reporter-htmlextra-export newman-report.html'
            }
        }
    }
}