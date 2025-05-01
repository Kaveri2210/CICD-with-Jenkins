
           pipeline {
    agent any

    environment {
        // Set up your Java and Maven versions
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'
        MAVEN_HOME = 'C:\\Users\\OWNER\\Downloads\\apache-maven-3.9.9'
    }

    tools {
        // Use Maven and JDK defined in Jenkins configuration
        maven 'Maven3.9.9'
        jdk 'JDK17'
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout code from the Git repository
                git 'https://github.com/Kaveri2210/CICD-with-Jenkins'
            }
        }

        stage('Build') {
            steps {
                // Run Maven clean and test
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' clean install"
                }
            }
        }

        stage('Test') {
            steps {
                // Run Maven test phase (run tests)
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' test"
                }
            }
        }

        stage('Post Actions') {
            steps {
                echo 'Post actions (e.g., notifications) can be done here.'
            }
        }
    }

    post {
        success {
            echo 'Build and tests successful.'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}

