pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'bin/rails db:reset'
                sh 'bin/rails db:migrate'
            }
        }
        stage('Test') {
            steps {
                sh 'bin/rails test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
