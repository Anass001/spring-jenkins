pipeline {
    agent any
    tools {
        maven 'Maven 3.8.6'
        jdk 'jdk17'
    }
    stages {
        stage('Checkout Codebase'){
            steps {
                echo 'polling..'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Anass001/spring-jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn install'
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