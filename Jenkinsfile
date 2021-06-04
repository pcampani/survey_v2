pipeline {
    stages {
        stage('Build') {
            agent { dockerfile true  }
            steps {
                echo 'Building..'
                sh 'docker-compose -f "docker-compose.yml" up -d --build'
            }
        }
        stage('Test') {
            agent { dockerfile true  }
            steps {
                echo 'Testing..'
                sh 'docker run survey-form-v2:latest sh -c "npm test"'
            }
        }
        stage('Compose Down') {
            agent { dockerfile true  }
            steps {
                echo 'Closing container....'
                sh 'docker-compose -f "docker-compose.yml" down'
            }
        }
    }
}