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
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                deploy adapters: [tomcat9(credentialsId: '39484b5f-6890-49f2-8e3f-faccaf60a90d', path: '', url: 'http://localhost:5050/')], contextPath: '**/*.war', war: ''
            }
        }
    }
}