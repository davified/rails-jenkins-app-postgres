pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'ruby -v'
                sh 'rails -v'
                sh 'bin/rails db:reset'
                sh 'bin/rails db:migrate'
                // echo 'building...'
            }
        }
        stage('Test') {
            steps {
                // sh 'bin/rails test'
                echo 'testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
