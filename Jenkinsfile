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
        deploy adapters: [tomcat9(path: '', url: 'http://18.224.66.164:8080/')], contextPath: 'web', war: '**/*.war'
 }
}
  }
}
}
