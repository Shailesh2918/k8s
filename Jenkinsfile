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
         sh 'az aks get-credentials --resource-group qa-aks-pot --name aksqa'
         sh 'kubectl apply -f web.yaml'
        }
      }
    }

  }

}
