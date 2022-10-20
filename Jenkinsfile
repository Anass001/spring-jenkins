pipeline {
    agent any

    stages {
        stage('Checkout Codebase'){
            steps {
                echo 'polling..'
                git 'https://github.com/Anass001/spring-jenkins'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}