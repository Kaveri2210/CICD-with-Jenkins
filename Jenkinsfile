
          pipeline {
    agent any

    tools {
        maven 'Maven 3.8.1'
        jdk 'Java 11'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Kaveri2210/CICD-with-Jenkins'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        failure {
            echo 'Build or tests failed.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}

