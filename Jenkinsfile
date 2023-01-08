pipeline {
    agent {
        docker {
            image 'gradle:6.6.1-jre14-openj9'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/repo/project.git'
            }
        }
        stage('Compile') {
            steps {
                script {
                    sh './gradlew compileJava'
                }
            }
        }
        stage('Unit Tests') {
            steps {
                script {
                    sh './gradlew test'
                }
            }
        }
    }
}
