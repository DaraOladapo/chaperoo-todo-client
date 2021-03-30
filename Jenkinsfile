pipeline{
        agent any
        stages{
            stage('Run App'){
                steps{
                    sh "sudo docker-compose pull && sudo -E DB_PASSWORD=root docker-compose up -d."
                }
            }
        }    
}
