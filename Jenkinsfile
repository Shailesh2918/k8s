pipeline {
	agent any


  stages {
	  stage('Checkout Source') {
		  steps {
			  checkout scm
		  }
	  }
	  
	  stage('kube file') {
		  steps {
			  withKubeConfig([credentialsId: 'user1', serverUrl: 'qaaks-1fe1ee75.aad70bae-5422-4738-a3f0-1c9b1ae4b2ab.privatelink.eastus2.azmk8s.io']) {
			  sh "az aks get-credentials --resource-group qa-aks-pot --name aksqa"
			  sh "kubectl apply -f web.yaml"
			  }
		  }
	  }
	 /*stage('Build') {
		  steps{
			  script {
				  
					  sh 'sudo docker login -u $ACR_USER -p $ACR_PASSWORD $ACR_SERVER'
					  //def imageWithTag = "$env.ACR_SERVER/$env.WEB_APP:$env.BUILD_NUMBER"
					 //image =  sh 'sudo podman build -t "$ACR_SERVER"/app:"$BUILD_NUMBER" .'
					  //image.push()
				         //sh 'sudo docker push "$ACR_SERVER"/app:"$BUILD_NUMBER"'
					 sh 'az acr build --image $ACR_SERVER"/app:"$BUILD_NUMBER  --registry qaingest.azurecr.io   --file Dockerfile .'
				  
				 }
			}
			 } */
	  
	  /*stage('Push image') {
		  steps{
			  script {
        
        docker.withRegistry('https://qaingest.azurecr.io', 'ssm-acr') {
	    //image =  sh 'sudo podman build -t "$ACR_SERVER"/app:"$BUILD_NUMBER" .'
            //image.push("${env.BUILD_NUMBER}")
            //image.push("latest")
		 sh 'sudo docker login -u $ACR_USER -p $ACR_PASSWORD $ACR_SERVER'
		sh 'az login'
		sh 'az account set -s d1804244-6fdc-43d9-a9bb-5f90f355eb66'
		sh 'az acr build --image $ACR_SERVER"/app:"$BUILD_NUMBER  --registry acrjenkins.azurecr.io   --file Dockerfile .'
            } 
                echo "Trying to Push Docker Build to registry"
    }
		  }
	  }*/
						  
}
						  }
