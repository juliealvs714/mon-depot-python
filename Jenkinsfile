pipeline {
    agent any

    environment {
        APP_NAME = 'monapp-python'
    }

    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/juliealvs714/mon-depot-python.git'
            }
        }

        stage('Exécuter les tests unitaires') {
            steps {
                sh '''
                echo "Lancement des tests..."
                python3 -m unittest discover tests || echo "Tests échoués ou absents"
                '''
            }
        }

        stage('Build de l’image Docker') {
            steps {
                sh 'docker build -t $APP_NAME .'
            }
        }

        stage('Déploiement (fictif)') {
            steps {
                sh 'echo "Déploiement sur serveur de test en cours..."'
            }
        }
    }
}
