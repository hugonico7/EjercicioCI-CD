pipeline {
  agent {
      docker { image 'gradle:6.6.1-jre14-openj9'}
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/hugonico7/EjercicioCI-CD.git'
      }
    }
    stage('Compile') {
      steps {
        sh './calculator/gradlew compileJava'
      }
    }
    stage('Unit Tests') {
      steps {
        sh './gradlew test'
      }
    }
  }
}
