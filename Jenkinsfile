#!/usr/bin/env groovy

pipeline {

    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'ssh jenkins@76.89.239.141 -p 8022 mkdir -p /home/jenkins-test'
                sh 'scp -P 8022 -r dist jenkins@6.89.239.141:/var/www/temp_deploy/dist/'
            }
        }
    }
}
