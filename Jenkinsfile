pipeline {
     agent any
     
     
  stages{
     stage('Build docker Image'){
          steps{
               sh ' docker build -t keerthi-sample-nodejs .'
               sh 'docker tag keerthi-sample-nodejs keerthi05/keerthi-sample-nodejs:latest'
               sh 'docker tag keerthi-sample-nodejs keerthi05/keerthi-sample-nodejs:$BUILD_NUMBER'
    }
     }
     
  stage('Push Image'){
          steps{
       withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {            
       sh 'docker push keerthi05/keerthi-sample-nodejs:latest'
       sh 'docker push keerthi05/keerthi-sample-nodejs:$BUILD_NUMBER'   
   }
}
}
     }
}
