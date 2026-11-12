pipeline {
    agent {
        docker{
            image 'postman/newman:latest'
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
                sh'npx newman run collections/collection.json -e env/preprod.json -r cli,htmlextra'
            }
        }
       
         
    }
}