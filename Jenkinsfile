pipeline {
    agent any

    parameters {
        string(name: 'VERSION', defaultValue:"1.0.0", description: "Build Version")
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage: Build -- Step1: Starting build... ...'
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Stage Test -- Step1: Starting testing... ...'
                sh './gradlew test'
            }
            post {
                always {
                    junit "build/reports/tests/test/*.xml"
                    publishHTML {
                        reportDir: "build/reports/tests/test",
                        reportFiles: "index.html",
                        reportName: "Test Report",
                        alwaysLinkToLastBuild: true,
                        allowMissing: true,
                        keepAll: true
                    }
                }
            }
        }
    }
}
