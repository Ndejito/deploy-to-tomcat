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
        deploy adapters: [tomcat9(credentialsId: 'UbuntuTomcat', path: '', url: 'http://3.144.104.200:8080/')], contextPath: 'myapp', war: '**/*.war'
 }
}
  }
}
}