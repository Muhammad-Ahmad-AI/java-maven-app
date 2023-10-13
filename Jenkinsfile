#!/usr/bin/env groovy

CODE_CHANGES = getGitChanges()

pipeline {
    agent none
    stages {
        stage('build') {
            steps {
                script {
                    echo "Building the application..."
                    echo ${CODE_CHANGES}
                }
            }
        }
        stage('test') {
            when {
                expression {
                    BRANCH_NAME == 'dev'
                }
            }
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
    post {
        always{
            echo "I always run"
        }
        success {
            echo "I run on success"
        }
    }
}
