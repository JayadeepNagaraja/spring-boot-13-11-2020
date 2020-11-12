pipeline{
agent any
  stages{
    stage('Checkout'){
      steps{
        git 'https://github.com/sharadrajore/spring-boot-jenkinsfile.git'
      }
    }
    stage('package'){
      steps{
        bat 'mvn clean package'
      }
    }
  }
}
