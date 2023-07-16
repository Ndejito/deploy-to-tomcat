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
        deploy adapters: [tomcat9(credentialsId: 'DeploytoTomcat', path: '', url: 'http://18.222.108.5:8080/')], contextPath: 'myapp', war: '**/*.war'
 }
}
  }
}
}