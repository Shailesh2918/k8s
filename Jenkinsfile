pipeline {

  environment {
    registry = "qaingest.azurecr.io/app1/kube-nginx-acr"
    dockerImage = ""
  }

  agent any

  stages {
 
    stage('Checkout Source') {
      steps {
                        git 'https://github.com/justmeandopensource/playjenkins.git'


      }
    }
stage('Build image') {
      steps{
        script {
          dockerImage = sh 'sudo podman build -t registry:"$BUILD_NUMBER" .'
        }
      }
    }
    
    

   /* stage('Deploy App') {
      steps {
        script {
        
         withKubeConfig([credentialsId: 'ssm-kube-1']) {
      sh 'kubectl apply -f web.yaml'
    }
        }
      }
    }*/

  }

}
