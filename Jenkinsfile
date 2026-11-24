pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Vérification des fichiers du projet MERN...'
                bat 'dir'
            }
        }

        stage('Build Docker Images') {
            steps {
                echo 'Construction des images Docker avec Docker Compose...'
                bat 'docker compose build'
            }
        }

        stage('Deploy Containers') {
            steps {
                echo 'Démarrage des conteneurs (MongoDB, Server, Client)...'
                bat 'docker compose up -d'
            }
        }

        stage('Verify Status') {
            steps {
                echo 'Vérification des conteneurs en cours d exécution...'
                bat 'docker compose ps'
            }
        }
    }
}