pipeline{
    agent any
    stages{
        stage("Pull latest image"){
            steps{
                sh "docker pull him323/selenium-docker"
            }
        }
        stage("Run the grid"){
            steps{
                 sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Tests"){

            steps{
                sh "docker-compose up search-module book-flight-module"
            }
        }

    }

    post{
        always {
            archiveArtifacts artifacts: "./output/**"
            sh "docker-compose down"
        }
    }

}