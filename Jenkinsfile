pipeline {
  agent any
  tools {
    maven 'Maven 3.8.6'
    jdk 'JDK21'
  }
  stages {
    stage('Clonar') {
      steps {
        git 'https://github.com/kamivillabla/saludoapp-ci.git'
      }
    }
    stage('Compilar') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Probar') {
      steps {
        bat 'mvn test'
      }
    }
    stage('Empaquetar') {
      steps {
        bat 'mvn package'
      }
    }
  }
  post {
    success {
      echo "Build exitoso"
    }
    failure {
      echo "El build fallo"
    }
  }
}
