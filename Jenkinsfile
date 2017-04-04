pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rails db:reset'
                sh 'rails db:migrate'
            }
        }
        stage('Test') {
            steps {
                sh 'rails test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
