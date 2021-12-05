pipeline{
  agent any
  
  stages{
    stage('Build'){
      withMaven(maven: 'Maven 3.8.4'){
        sh 'clean compile'
      }
    }
    
    stage('Test'){
      withMaven(maven: 'Maven 3.8.4'){
        sh 'mvn test'
      }
    }
  }
}
