pipeline {
    agent any
    stages {
        stage('Checkout') {
            checkout scm
        }

        stage('Build & UnitTest') {
            steps {
                sh "docker build -t survey-form-v2:latest -f Dockerfile ."
                sh "docker build -t survey-form-v2:latest:test-B${BUILD_NUMBER} -f Dockerfile.Integration ."
            }
        }  
    }
}