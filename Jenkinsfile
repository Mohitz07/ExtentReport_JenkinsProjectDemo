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
                    reportName: 'Extent Report',
                    reportDir: 'target',                 // dir that contains the HTML file
                    reportFiles: 'ExtentReport.html'     // or e.g. 'cucumber-reports/index.html'
                ])
            }
        }
    }
}
