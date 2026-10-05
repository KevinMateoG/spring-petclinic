#!groovy

pipeline {
  agent none // No usa un agente global, cada etapa define el suyo
  
  stages {
    stage('Maven Build and Package') {
      agent {
        docker {
          image 'maven:3.9-eclipse-temurin-25' 
          reuseNode true
        }
      }
      steps {
        // Aquí es donde Jenkins levanta el contenedor de Maven y ejecuta el comando con éxito
        sh 'mvn clean package -DskipTests'
      }
    }
  }
}