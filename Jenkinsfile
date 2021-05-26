pipeline {

  

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/shilpa12345/k8s.git'
      }
    }

    
    

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "web.yaml", kubeconfigId: "ssm-kube")
        }
      }
    }

  }

}
