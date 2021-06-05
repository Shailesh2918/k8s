pipeline {
	agent any


  stages {
	  stage('Checkout Source') {
		  steps {
			  checkout scm
		  }
	  }
	  
	 /* stage('Build') {
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
	    image =  sh 'sudo podman build -t "$ACR_SERVER"/app:"$BUILD_NUMBER" .'
            //image.push("${env.BUILD_NUMBER}")
            image.push("latest")
            } 
                echo "Trying to Push Docker Build to registry"
    }
		  }*/
	  }
						  
}
						  }
