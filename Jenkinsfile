pipeline {
    agent {
        docker {
            image 'php:7'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'phpunit --version'
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development' 
            }
            steps {
                sh 'phpunit --verbose MultipleDependenciesTest'
            }
        }
        stage('Deploy for production') {
            when {
                branch 'master'  
            }
            steps {
                sh 'phpunit --verbose MultipleDependenciesTest'
            }
        }
    }
}
