pipeline{
agent any
  stages{
   
    stage('package'){
      steps{
        bat 'mvn clean package'
      }
    }
    stage('Deploy'){
      steps{
        deploy adapters: [tomcat9(credentialsId: 'tomcat-users', path: '', url: '')], contextPath: 'spring-boot', war: '**/*.war'
      }
    }
    
  }
}
