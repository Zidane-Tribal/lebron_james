pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository
                git url: 'https://github.com/Zidane-Tribal/lebron_james.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Add your build steps here
                // Example for a Java Maven project:
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Add your test steps here
                // Example for running unit tests:
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deployment steps can go here (e.g., deploy to a server or cloud)
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            // Archive build results or send notifications
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}

