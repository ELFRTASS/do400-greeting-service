pipeline{
    agent {
        kubernetes {
            inheritFrom 'nodejs'
            defaultContainer 'nodejs'
            serviceAccount 'jenkins'
        }
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

        // Add the "Deploy" stage here
    }
}
