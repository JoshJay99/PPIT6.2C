pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
            post{
                always{
                    main to: "sherlockjay03@gmail.com",
                    subject: "Build status email",
                    body: "Build log attached",
                }
            }
        }
        stage("Test"){
            steps{
                echo "Testing..."
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploying..."
            }
        }
    }
}
               
