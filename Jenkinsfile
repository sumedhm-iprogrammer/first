pipeline {
    agent any
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
                sh 'phpunit MultipleDependenciesTest'
            }
        }
    }
}
