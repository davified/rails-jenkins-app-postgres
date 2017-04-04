pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '$export PATH="$HOME/.rbenv/shims:$PATH"'
                sh 'rbenv global 2.3.0'
                sh 'rbenv rehash'
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
