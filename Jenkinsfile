node ('master')  {
  checkout scm
  
  stage('Build') {
    withMaven(maven: 'M3') {
      bat 'mvn -Dmaven.test.failure.ignore clean package'
    }
  }
  
  stage('Results') {
    junit '**/target/surefire-reports/TEST-*.xml'
    archiveArtifacts 'target/*.jar'
  }
}
