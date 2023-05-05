pipeline {
    agent any

    tools {
        maven 'Maven'
    }
    stages{
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'
            }
            post {
                always {
                    mail to: "sherlockjay03@gmail.com",
                         subject: "Build status email",
                         body: "Build log attached"
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                sh 'mvn sonar:sonar'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities...'
                sh 'dependency-check.sh --project MyProject --scan ./'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Add your custom deployment script for staging
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Add your custom integration testing script for staging
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Add your custom deployment script for production
            }
        }
    }
}
