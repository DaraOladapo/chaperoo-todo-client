pipeline{
        agent any
        stages{
            stage('Run App'){
                steps{
                    sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d."
                }
            }
        }    
}
