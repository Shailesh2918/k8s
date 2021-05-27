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
    
     /*stage('Push image') {
        steps{
        script {
        docker.withRegistry('https://qaingest.azurecr.io', 'ssm-acr') {
		dockerImage.push("${env.BUILD_NUMBER}") 
		dockerImage.push('latest') 
            } 
	}
	}
               
    }*/


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
