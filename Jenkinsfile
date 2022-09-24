pipeline {
  agent any
  tools {
    maven 'Maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install -DskipTest'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: 'Deployer', path: '', url: 'http://34.238.172.192/:8080')], contextPath: '/web', onFailure: false, war: '**/hello-world.war'
      }
     }
   }
 }
}

