pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Estherblanche/demo-web.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
    }
}