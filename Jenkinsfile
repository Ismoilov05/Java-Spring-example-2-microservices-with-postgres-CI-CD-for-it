pipeline {
    agent any

    stages {

        stage('Build User Service') {
            steps {
                dir('user-service') {
                    sh './mvnw clean package -DskipTests'
                }
            }
        }

        stage('Build Order Service') {
            steps {
                dir('order-service') {
                    sh './mvnw clean package -DskipTests'
                }
            }
        }

        stage('Docker Build') {
             steps {
        sh '''
            echo "=== Docker version ==="
            docker version

            echo "=== Docker compose version ==="
            docker compose version

            echo "=== Docker info ==="
            docker info

            echo "=== Current directory ==="
            pwd
            ls -la

            echo "=== Docker Compose Build ==="
            docker compose build
        '''
    }
        }
    }
}