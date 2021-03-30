pipeline{
        agent any
        environment {
            app_version = 'v4'
            rollback = 'false'
            DB_PASSWORD='root'
        }
        stages{
            stage('Build Image'){
                steps{
                    script{
                        if (env.rollback == 'false'){
                            image = docker.build("daraoladapo/chaperoo-frontend")
                        }
                    }
                }
            }
            stage('Tag & Push Image'){
                steps{
                    script{
                        if (env.rollback == 'false'){
                            docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials'){
                            }
                        image.push("${env.app_version}")
                        }
                    }
                }
            }
            stage('Deploy App'){
                steps{
                    sh "docker-compose pull && docker-compose up -d"
                }
            }
        }
}