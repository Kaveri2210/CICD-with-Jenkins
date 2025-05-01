
            pipeline {
    agent any

    tools {
        jdk 'JDK17'        // You must configure this in Jenkins > Global Tool Configuration
        maven 'Maven3.9'   // You must configure this in Jenkins > Global Tool Configuration
    }

    environment {
        PATH = "${tool 'Maven3.9'}/bin:${env.PATH}"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
