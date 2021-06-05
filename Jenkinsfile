pipeline {
    agent any
    stages {
        node('docker') {
            stage 'Checkout'
                checkout scm
            
            stage 'Build & UnitTest'
                sh "docker build -t survey-form-v2:latest -f Dockerfile ."
                sh "docker build -t survey-form-v2:latest:test-B${BUILD_NUMBER} -f Dockerfile.Integration ."
        }
    }
    
}