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
          kubernetesDeploy(configs: "web.yaml", kubeconfigId: "ssm-kube-1")
        }
      }
    }

  }

}
