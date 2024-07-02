pipeline {
   agent any

   stages {
      stage('clean') {
         steps {
            bat 'mvn clean'
         }
      }
      stage('package') {
         steps {
            bat 'mvn install'
         }
      }
      stage('deploy') {
         steps {
            deploy adapters: [tomcat9(credentialsId: 'ed2e2efa-21ef-46cc-a124-ab453f238012', path: '', url: 'http://localhost:9999')], contextPath: 'weguideJune24', war: 'productweb\\target\\productweb.war'
         }
      }
   }
  
}
