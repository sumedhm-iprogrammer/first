pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'wget https://phar.phpunit.de/phpunit-6.5.phar'
                sh 'chmod +x phpunit-6.5.phar'
                sh 'mv phpunit-6.5.phar /usr/local/bin/phpunit'
            }
        }
        stage('Test') {
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
