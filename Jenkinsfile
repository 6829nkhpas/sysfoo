pipeline {
  agent any
   tools{
     maven 'maven 3.9.6'
   }
  stages{
      stage("build"){
          steps{
              echo 'complile the sysgoo app ....'
            sh 'mvn compile'
              
          }
      }
      stage("two"){
          steps{
              echo 'Running the tests ...'
              sh 'mvn clean test'
          }
      }
      stage("three"){
          steps{
              echo 'Packaging the app ...'
              sh 'mvn package -DskipTests'
          }
      }
  }

  post{
    always{
        echo 'This pipeline is completed..'
    }
  }
}

