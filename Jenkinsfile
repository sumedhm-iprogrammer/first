
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'php --version'
            }
        },
        stage('Unit Test') {
            steps {
                sh 'php -r "echo php_info();"'
            }
        }
    }
}
