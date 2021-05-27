pipeline {

  

  agent any

  stages {

    stage('Checkout Source') {
      steps {
                checkout scm

      }
    }

    
    

    stage('Deploy App') {
      steps {
        script {
        
         withKubeConfig([credentialsId: 'ssm-kube-1', serverUrl: 'https://qaaks-1fe1ee75.aad70bae-5422-4738-a3f0-1c9b1ae4b2ab.privatelink.eastus2.azmk8s.io']) {
      sh 'kubectl apply -f web.yaml'
    }
        }
      }
    }

  }

}
