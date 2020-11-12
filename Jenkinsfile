pipeline{
agent any
  stages{
   
    stage('package'){
      steps{
        bat 'mvn clean package'
      }
    }
   
    stage('Build Docker Image'){
      steps{
        bat 'docker build -t sharadrajore/my-app:2.0.0 .'
      }
    }
    stage('Docker Image Push'){
      steps{
        withCredentials([string(credentialsId: 'DockerCred', variable: 'DockerPwd')]) {
          bat "docker login -u sharadrajore -p ${DockerPwd}"
        }
        bat 'docker push sharadrajore/my-app:2.0.0'
      }
     } 
     stage('Run Container'){
       steps{
        bat 'docker run -p 8080:8080 -d sharadrajore/my-app:2.0.0'
      }
    }
    
  }
}
