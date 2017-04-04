pipeline {
    agent any

    stages {
        stage('Build') {
            properties([pipelineTriggers([[$class: 'GitHubPushTrigger'], pollSCM('H/1 * * * *')])])
            steps {
                sh 'pwd'
                sh 'ls -la'
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
