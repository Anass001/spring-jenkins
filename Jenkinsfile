pipeline {
    agent any

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
                build 'spring-boot-pipeline'
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