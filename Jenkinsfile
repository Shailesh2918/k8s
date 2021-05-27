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
        
         sh 'kubectl apply -f web.yaml'
        }
      }
    }

  }

}
