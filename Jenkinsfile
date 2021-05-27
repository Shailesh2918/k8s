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
        
         withKubeConfig([credentialsId: 'ssm-kube-1']) {
      sh 'kubectl apply -f web.yaml'
    }
        }
      }
    }

  }

}
