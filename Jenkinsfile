pipeline {

  environment {
    registry = "qaingest.azurecr.io/app1/kube-nginx-acr"
    dockerImage = ""
CONTAINER_REGISTR='qaingest.azurecr.io'
AZURE_SUBSCRIPTION_ID='d1804244-6fdc-43d9-a9bb-5f90f355eb66'
RESOURCE_GROUP='qa-aks-pot'
	  REPO="kube-nginx-acr"
        IMAGE_NAME="nginx"
        TAG="v2"
  }

  agent any

  stages {
 
    stage('Checkout Source') {
      steps {
       checkout scm
      }
    }
/*stage('Build image') {
      steps{
        script {
          dockerImage = sh 'sudo podman build -t registry:"$BUILD_NUMBER" .'
        }
      }
    }*/
    
     /*stage('Push image') {
        steps{
        script {
        docker.withRegistry('https://qaingest.azurecr.io', 'ssm-acr') {
		sh 'az acr login --name $CONTAINER_REGISTRY --resource-group $RESOURCE_GROUP'
                sh 'az acr build --image $REPO/$IMAGE_NAME:$TAG --registry $CONTAINER_REGISTRY --file Dockerfile . '
            } 
	}
	}
               
    }*/

stage('Build') {
    steps{
        script {
    withCredentials([usernamePassword(credentialsId: ssm-acr, usernameVariable: 'ACR_USER', passwordVariable: 'ACR_PASSWORD')]{
      sh 'docker login -u $ACR_USER -p $ACR_PASSWORD https://$ACR_SERVER'
      // build image
      def imageWithTag = "$env.ACR_SERVER/$env.WEB_APP:$env.BUILD_NUMBER"
      def image = docker.build imageWithTag
      // push image
      image.push()
    }
		    }
    }
		    }
   /*stage('Deploy App') {
      steps {
        script {
        
         withKubeConfig([credentialsId: 'ssm-kube-1']) {
      sh 'kubectl apply -f web.yaml'
    }
        }
      }
    } */
	  
	  
	/*stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "web.yaml", kubeconfigId: "ssm-kube-1")
        }
      }
    }*/
    
    }

}
