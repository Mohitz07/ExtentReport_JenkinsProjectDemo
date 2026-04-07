pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mohitz07/ExtentReport_JenkinsProjectDemo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Report') {
    steps {
        publishHTML([
            target: [
                reportName: 'Extent Report',
                reportDir: 'target/ExtentReport.html',      // or 'target/cucumber-reports'
                reportFiles: 'ExtentReport.html'               // or 'report.html'
            ]
        ])
    }
}
    }
}
