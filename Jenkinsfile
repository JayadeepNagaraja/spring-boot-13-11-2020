pipeline{
agent any
  stages{
    stage('Checkout'){
      git 'https://github.com/sharadrajore/spring-boot-jenkinsfile.git'
    }
    stage('package'){
      bat 'mvn clean package'
    }
  }
}
