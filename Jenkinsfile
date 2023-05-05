pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'
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
        stage('Deploy to Production'){
            steps{
                post {
                    always {
                        mail to: "sherlockjay03@gmail.com",
                             subject: "Build status email",
                             body: "Build log attached"
                }
            }
    }
}
