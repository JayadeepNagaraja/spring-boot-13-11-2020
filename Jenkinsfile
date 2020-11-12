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
        deploy adapters: [tomcat9(credentialsId: 'tomcat-users', path: '', url: 'http://localhost:8080/')], contextPath: 'spring-boot', war: '**/*.war'
      }
    }
    stage('Build Docker Image'){
      bat 'docker build -t sharadrajore/my-app:2.0.0 .'
    }
    
  }
}
