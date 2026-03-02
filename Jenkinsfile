pipeline {
    agent any

    stages {

        stage('Cloner le code') {
            steps {
                echo 'Clonage du projet...'
                checkout scm
            }
        }

        stage('Build avec Maven') {
            steps {
                echo 'Compilation du projet...'
                bat 'mvn clean package'
            }
        }

        stage('Déploiement sur Tomcat') {
            steps {
                echo 'Déploiement vers Tomcat...'
                bat '''
                copy /Y target\\demo-web.war C:\\Users\\AZIMUT\\apache-tomcat-9.0.115\\webapps\\
                '''
            }
        }
    }

    post {
        success {
            echo 'Déploiement réussi 🚀'
        }
        failure {
            echo 'Échec du pipeline ❌'
        }
    }
}