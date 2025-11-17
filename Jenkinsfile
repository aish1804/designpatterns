pipeline {
    agent any

    parameters {
        string(name: 'VERSION', defaultValue:"1.0.0", description: "Build Version")
    }

    stages {
        stage('Build') {
            steps {
                echo 'Step1: Starting build... ...'
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                echo 'Step1: Starting testing... ...'
                sh './gradlew test'
            }

        }
    }
}
