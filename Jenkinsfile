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
                sh 'docker compose build'
            }
        }
    }
}