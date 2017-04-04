pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                pwd
                ls -la
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
