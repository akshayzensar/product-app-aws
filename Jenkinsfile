pipeline {
    agent any

    tools {
        maven 'maven3'
        jdk 'jdk11'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/akshayzensar/product-app-aws.git'
            }
        }

        stage('Build') {
            steps {
                bat 'java -version'
                bat 'mvn -version'
                bat 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'Build successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
