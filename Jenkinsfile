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
				  withCredentials([usernamePassword(credentialsId: ssm-acr, usernameVariable: 'ACR_USER', passwordVariable: 'ACR_PASSWORD')]{
					  sh 'docker login -u $ACR_USER -p $ACR_PASSWORD https://$ACR_SERVER
					  def imageWithTag = "$env.ACR_SERVER/$env.WEB_APP:$env.BUILD_NUMBER"
					  def image = docker.build imageWithTag
					  image.push()
				  }
						  }
						  }
						  }
						  }
						  }
