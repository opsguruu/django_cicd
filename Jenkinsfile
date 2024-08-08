pipeline {
    agent any

    environment{
        DOCKER_IMAGE_NAME = "django_cicd-django"
    }

    stages {
        stage('Build') {
            steps {
                               // Run Maven on a Unix agent.
                sh 'sudo docker-compose down'
                sh 'sudo docker-compose build'
            }

        }
        
        stage('Deploy') {
            when {
                branch 'production'
            }
            steps{
                sh 'sudo docker-compose up -d'
            }
        }  
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps{
                sh 'sudo docker-compose up -d'
            }
        }    
    }
}

