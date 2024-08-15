pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build - Compiling and packaging the code.'
                // Tool: Maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests - Running unit and integration tests.'
                // Tools: JUnit, TestNG
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Pipeline: Unit and Integration Tests - ${currentBuild.currentResult}",
                        body: "The Unit and Integration Tests stage has completed with status: ${currentBuild.currentResult}.",
                        to: 'youremail@example.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis - Analyzing the code for quality and standards.'
                // Tool: SonarQube
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan - Scanning the code for vulnerabilities.'
                // Tool: OWASP Dependency-Check
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Pipeline: Security Scan - ${currentBuild.currentResult}",
                        body: "The Security Scan stage has completed with status: ${currentBuild.currentResult}.",
                        to: 'jhamb.saksham2408@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging - Deploying the application to a staging server.'
                // Tool: AWS CLI
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging - Running integration tests on staging.'
                // Tools: JUnit, TestNG
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production - Deploying the application to a production server.'
                // Tool: AWS CLI
            }
        }
    }
}
