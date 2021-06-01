pipeline {
	agent any

  stages {
	  stage('Checkout Source') {
		  steps {
			  checkout scm
		  }
	  }
	  
	  stage('Build') {
		  steps{
			  script {
				  
					  sh 'sudo podman login -u $ACR_USER -p $ACR_PASSWORD https://$ACR_SERVER'
					  //def imageWithTag = "$env.ACR_SERVER/$env.WEB_APP:$env.BUILD_NUMBER"
					  def image = sh 'sudo podman build -t $env.ACR_SERVER/app:$env.BUILD_NUMBER .'
					  image.push()
				  
				 }
			}
			 }
						  
}
						  }
