pipeline {
    agent any
    stages {
        stage('Build') {
            agent any
            steps {
                echo 'Building..'
                sh 'docker-compose -f "docker-compose.yml" up -d --build'
            }
        }
        stage('Test') {
            agent any
            steps {
                echo 'Testing..'
                sh 'docker run survey-form-v2:latest sh -c "npm test"'
            }
        }
        stage('Compose Down') {
            steps {
                echo 'Closing container....'
                sh 'docker-compose -f "docker-compose.yml" down'
            }
        }
    }
}