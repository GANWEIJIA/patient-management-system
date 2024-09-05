pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/GANWEIJIA/patient-management-system'
            }
        }
        stage('Build') {
            steps {
                powershell './gradlew.bat clean build'  // Ensure you're using gradlew.bat for Windows
            }
        }
        stage('Test') {
            steps {
                powershell './gradlew.bat test'  // Again, use gradlew.bat
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace'
            deleteDir()
        }
    }
}