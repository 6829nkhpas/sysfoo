pipeline {
  agent none
  stages {
    stage('build') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17-alpine'
        }

      }
      steps {
        echo 'complile the sysgoo app ....'
        sh 'mvn compile'
      }
    }

    stage('two') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17-alpine'
        }

      }
      steps {
        echo 'Running the tests ...'
        sh 'mvn clean test'
      }
    }

    stage('three') {
      agent {
        docker {
          image 'maven:3.9.6-eclipse-temurin-17-alpine'
        }

      }
      steps {
        echo 'Packaging the app ...'
        sh 'mvn package -DskipTests'
      }
    }

  }
  tools {
    maven 'maven 3.9.6'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}