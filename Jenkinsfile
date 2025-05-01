pipeline {
    agent any

    environment {
        // Environment variables for Java and Maven installations
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'  // Adjust as per your JDK installation path
        MAVEN_HOME = 'C:\\Users\\OWNER\\Downloads\\apache-maven-3.9.9'  // Adjust as per your Maven path
    }

    tools {
        // Tool configuration in Jenkins (configured in Global Tool Configuration)
        maven 'Maven3.9.9'  // Name configured in Jenkins for Maven
        jdk 'JDK17'  // Name configured in Jenkins for JDK
    }

    stages {
        // Stage for Checking out the code from the Git repository
        stage('Checkout Code') {
            steps {
                // Fetch the code from the Git repository
                git 'https://github.com/Kaveri2210/CICD-with-Jenkins'  // Use your repository URL here
            }
        }

        // Stage for Building the project with Maven
        stage('Build') {
            steps {
                // Execute Maven clean install command to build the project
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' clean install"  // Build the project using Maven
                }
            }
        }

        // Stage for Running Tests
        stage('Test') {
            steps {
                // Execute Maven test command to run the tests (TestNG)
                script {
                    sh "'${MAVEN_HOME}/bin/mvn' test"  // Run tests using Maven
                }
            }
        }

        // Stage for Post Actions (like notifications, deployments, etc.)
        stage('Post Actions') {
            steps {
                echo 'Post actions (notifications, deployment) can be added here.'
            }
        }
    }

    // Post build actions: handling success and failure
    post {
        success {
            echo 'Build and tests successful!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
