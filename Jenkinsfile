pipeline {
  agent any
  tools {
    maven 'Maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: 'Tomcat', path: '', url: 'http://3.145.204.215:8080/')], contextPath: '/web', war: '**/*.war'
   }
 }
}
  }
}
