pipeline {

  

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git'
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
