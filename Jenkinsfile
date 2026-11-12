pipeline {
    agent {
        docker{
            image 'sbx/playwright:latest'
            args '-u root --entrypoint='
        }
    }
    stages {
         stage('Check version nodejs') {
            steps {
                sh 'newman --version'
                sh 'npm --version'
            }
        }
        stage('install dep') {
            steps {
                sh 'npm install'
            }
        }
        stage('Lancer le test') {
            steps {
                sh'npx playwright test'
            }
        }
       
         
    }
}