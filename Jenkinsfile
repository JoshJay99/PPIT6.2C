pipeline {
    agent any
    stages{
        stage('Build') {
            steps {
                echo 'Building the code using Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests with JUnit'
            }
            post {
                success {
                    mail to: "sherlockjay03@gmail.com",
                         subject: "Build status email",
                         body: "Successful build log attached"
                }
                failure {
                    mail to: "sherlockjay03@gmail.com",
                         subject: "Build status email",
                         body: "Successful build log attached"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Using SonarQube to an analyise the code'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Using OWASP Dependancy check to scan the code'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Using AWS to deploy the code to staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Using JUnit again to run tests on staging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Using AWS again to deploy to production'
            }
        }
    }
}
