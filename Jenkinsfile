pipeline{
    agent any
    stages{
        stage("Run the grid"){
            steps{
                 sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Tests"){

            steps{
                sh "docker-compose up search-module search-module2"
            }
        }

        stage("Bring down services"){
            steps{
                sh "docker-compose down"
            }
        }
    }

}