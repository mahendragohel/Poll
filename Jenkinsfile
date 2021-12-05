pipeline{
  agent any
  tools { 
        maven 'Maven 3.8.4'
    }
  stages{
    stage('Build'){
      steps{
          sh 'clean compile'
      }
      post {
          // If Maven was able to run the tests, even if some of the test
          // failed, record the test results and archive the jar file.
          success {
              junit '**/target/surefire-reports/TEST-*.xml'
              archiveArtifacts 'target/*.jar'
          }
      }
    }
    
    stage('Test'){
      steps{
          sh 'mvn test'
      }
    }
  }
}
