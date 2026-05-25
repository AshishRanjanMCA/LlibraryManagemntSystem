pipeline {

    agent any

    environment {
        APP_NAME = "library-management-app"
        CONTAINER_NAME = "library-management-container"
    }

    tools {
        jdk 'JDK21'
        maven 'Maven'
    }

    stages {

        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/AshishRanjanMCA/LlibraryManagemntSystem.git'
            }
        }

        stage('Build Maven Project') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $APP_NAME .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop $CONTAINER_NAME || true
                docker rm $CONTAINER_NAME || true
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker run -d \
                --name $CONTAINER_NAME \
                -p 9090:8080 \
                $APP_NAME
                '''
            }
        }

    }

    post {

        success {
            echo 'Application deployed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }

    }
}
