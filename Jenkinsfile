pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'phpunit --version'
            }
        }
        stage('Deliver for Production') {
            when {
                branch 'master' 
            }
            steps {
                sh 'phpunit MultipleDependenciesTest'
                sh 'echo "Released!!!"'
            }
        }
    }
}
